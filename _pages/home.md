---
layout: splash
permalink: /
title: "About me"
excerpt: "Dong Ho Lee — Ph.D. student at UT Austin studying games of ordered preference, numerical optimization, and multi-agent control."
classes: portfolio-home
---

<div class="research-intro">
  <div>
    <h1>Dong Ho Lee</h1>
    <p>Hi! I am a Ph.D. student in Aerospace Engineering at the University of Texas at Austin. I work in the <a href="https://clearoboticslab.github.io/">CLeAR Lab</a>, advised by Prof. David Fridovich-Keil.</p>
    <p>My research interests are optimization, game theory, control, and learning for multi-agent systems. I study how agents make decisions when some objectives take priority over others. My current work develops compact reformulations and a Newton solver for real-time receding-horizon control. I implement these methods in Julia and Python.</p>
    <p>Before joining UT Austin, I received my B.S. and M.S. in Aerospace Engineering at KAIST and worked on UAV mission planning at the Agency for Defense Development.</p>
    <p>I am looking for research internship opportunities in 2027.</p>
  </div>
  <figure class="research-portrait">
    {% assign portrait_file = site.static_files | where: "path", "/assets/images/DongHo-profile.jpg" | first %}
    <img src="{{ '/assets/images/DongHo-profile.jpg' | relative_url }}?v={{ portrait_file.modified_time | date: '%s' }}" alt="Portrait of Dong Ho Lee" width="800" height="1200">
    <figcaption>
      <nav class="profile-icons" aria-label="Profile links">
        <a href="mailto:leedh0124@utexas.edu" aria-label="Email" title="Email"><i class="fas fa-envelope" aria-hidden="true"></i></a>
        <a href="https://scholar.google.com/citations?user=8w4oBHAAAAAJ&amp;hl=en" aria-label="Google Scholar" title="Google Scholar"><i class="fas fa-graduation-cap" aria-hidden="true"></i></a>
        <a href="https://github.com/leedh0124" aria-label="GitHub" title="GitHub"><i class="fab fa-github" aria-hidden="true"></i></a>
        <a href="https://www.linkedin.com/in/dong-ho-lee-708551147/" aria-label="LinkedIn" title="LinkedIn"><i class="fab fa-linkedin" aria-hidden="true"></i></a>
        <a href="{{ site.data.documents.resume | relative_url }}" aria-label="Resume (1 page)" title="Resume (1 page)"><i class="fas fa-file-alt" aria-hidden="true"></i></a>
      </nav>
      Austin, Texas<br>Ph.D. expected May 2028
    </figcaption>
  </figure>
</div>

## Research in focus

<div class="research-grid">
  <article class="research-card">
    <p class="eyebrow">Current work</p>
    <h3>Planning with ordered objectives</h3>
    <p>Receding-horizon control for highway overtaking and cooperative pot transfer.</p>
    <a href="{{ '/projects/#current-work' | relative_url }}">Read more →</a>
  </article>
  <article class="research-card">
    <p class="eyebrow">Prior work</p>
    <h3>Games of Ordered Preference</h3>
    <p>A framework for strategic agents with strictly ordered objectives, and compact reformulations for computation.</p>
    <a href="{{ '/projects/#ordered-preferences' | relative_url }}">Read more →</a>
  </article>
  <article class="research-card">
    <p class="eyebrow">Prior work</p>
    <h3>Hierarchical routing</h3>
    <p>A convex reformulation and branch-and-bound solver for route assignment with strategic vehicle interactions.</p>
    <a href="{{ '/projects/#hierarchical-routing' | relative_url }}">Read more →</a>
  </article>
</div>

## Selected publications

{% assign selected_papers = site.data.publications | where: "featured", true %}
{% for paper in selected_papers %}
{% include publication-entry.html paper=paper %}
{% endfor %}

<p class="content-updated">Updated November 6, 2026</p>
