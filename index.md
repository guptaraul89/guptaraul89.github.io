---
layout: cv
title: Rahul Gupta - Resume
jsarr:
- js/scripts.js
---

<!-- Header Section -->
<h1 id="cv-title" style="grid-column: text-start / page-end;"><a href="{{ site.url }}"> {{ site.title | default: "Rahul Gupta" }} </a></h1>
<p id="cv-subtitle" style="grid-column: text-start / page-end;"><i> {{ site.tagline | default: "Lead Data Engineer @ Cadent TV" }} </i></p>

<!-- Intro Section: Image Left, Text Right -->
<!-- Using display: contents to make children direct grid items of the parent layout -->
<div id="intro-container" style="grid-column: page-start / page-end; display: contents;">

    <!-- Column 1: Profile Image -->
    <div id="profile-image-container" style="grid-column: page-start / middle-start; padding-right: 1.5rem; align-self: start; margin-top: 1rem;">
        <!-- Ensure /images/profile.jpeg is the correct path -->
        <img src="/images/profile.jpeg" alt="Profile picture of Rahul Gupta" style="width: 400%; max-width: 250px; /* Adjust this size */ height: auto; border-radius: 8px; display: block;">
    </div>

    <!-- Column 2: Summary Text & Social Links -->
    <div id="intro-text-links-container" style="grid-column: text-start / page-end; margin-top: 1rem;">
        <div style="text-align: justify;">
            <!-- **** YOUR SUMMARY TEXT **** -->
            
            My data engineering expertise centers on designing and implementing highly scalable, low-latency systems specifically tailored for the demanding Ad Tech and real-time bidding (RTB) environments. I specialize in tackling the unique challenges posed by processing terabytes of data and billions of events daily, often under strict sub-200ms latency constraints for core auction mechanics. This involves architecting robust cloud-native solutions, developing sophisticated data pipelines, and optimizing data access through techniques like advanced partitioning, key-value store optimization, and efficient data aggregation strategies.
            
            <p>
            The impact of these engineered solutions is concrete: significant reductions in infrastructure costs (CPU, storage, data transfer), substantial performance gains (faster lookups, higher throughput, optimized ingestion, sub-millisecond filtering), and vastly improved system stability and scalability for critical ad exchange platforms. Meeting these standards is crucial for enabling real-time analytics, boosting operational efficiency, unlocking revenue potential, and ensuring top-tier data transparency.
            </p>
        </div>
        <!-- Highlights -->
        <p style="margin-top: 1rem;"><b>Highlights:</b> 4 Publications | 4 Awards | 20 Manuscripts Reviewed | 7 Judged </p>

        <!-- Social Links -->
        <div class="cv-image-links-wrapper" style="margin-top: 1.5rem;">
             <div class="cv-image-links">
                 {% for link in site.data.social-links %}{% if link.cv-group == 1 %}{% include social-link.html link=link %}{% endif %}{% endfor %}
             </div>
             <div class="cv-image-links">
                 {% for link in site.data.social-links %}{% if link.cv-group == 2 %}{% include social-link.html link=link %}{% endif %}{% endfor %}
             </div>
        </div>
    </div>

</div><!-- End intro-container -->

<!-- Separator -->
<hr style="grid-column: text-start / page-end;">

## Work Experience
{::nomarkdown}
{% for experience in site.data.experiences %}
{% if experience.type == "industry"%}
{% include cv/experience.html experience=experience %}
{% endif %}
{% endfor %}
{:/}

## Education
{::nomarkdown}
{% for degree in site.data.education %}
{% include cv/degree.html degree=degree %}
{% endfor %}
{:/}


## Publications

{% assign selectedBoolForBibtex = true %}
{::nomarkdown}
{% assign selected = site.data.publications | where: 'type', "conference" %}
{% for pub in selected %}
{% include cv/publication.html pub=pub %}
{% endfor %}
{:/}

## Memberships

{% for item in site.data.membership %}
{% include cv/membership.html membership=item %}
{% endfor %}


## Peer-Reviewing & Judging

{% for venue in site.data.reviewer %}
{% include cv/venue.html venue=venue %}
{% endfor %}

{% assign talktitles = site.data.talks | group_by:"title" %}
{% for title in talktitles %}
{% include cv/talk.html talk=title %}
{% endfor %}


{% assign talktitles = site.data.university_lectures | group_by:"title" %}
{% for title in talktitles %}
{% include cv/university_lectures.html talk=title %}
{% endfor %}


## Selected Honors and Awards

{% for award in site.data.awards %}
{% include cv/award.html award=award %}
{% endfor %}


## Press Coverage

{% for press in site.data.press %}
{% include cv/press.html press=press %}
{% endfor %}


## Articles and Blogs

{% for blogs in site.data.blogs %}
{% include cv/blogs.html blogs=blogs %}
{% endfor %}
