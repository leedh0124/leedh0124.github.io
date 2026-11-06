---

permalink: /publication/
title: "Publications"
excerpt: "Research publications by Dong Ho Lee on multi-agent games, hierarchical optimization, reinforcement learning, and robotics."
classes: wide
---

## Preprints

{% assign papers = site.data.publications | where: "kind", "preprint" %}
{% for paper in papers %}{% include publication-entry.html paper=paper %}{% endfor %}

## Journal publications

{% assign papers = site.data.publications | where: "kind", "journal" %}
{% for paper in papers %}{% include publication-entry.html paper=paper %}{% endfor %}

## Conference publications

{% assign papers = site.data.publications | where: "kind", "conference" %}
{% for paper in papers %}{% include publication-entry.html paper=paper %}{% endfor %}

## Earlier publications in Korea

- **Dong Ho Lee**, Hwanchol Jang, Sang-Hwan Kim, and Woohyuk Chang. “Multi-UAV Mission Allocation and Optimization Technique Based on Discrete-Event Modeling and Simulation.” *Journal of the Korean Society for Aeronautical & Space Sciences*, 48(2), 159–166 (2020).
- **Dong Ho Lee**, Woohyuk Chang, and Jinku Buyn. “An Optimization Technique for Discrete Event Model-based UAV Real-Time Heterogeneous Mission Allocation.” *Korean Society for Aeronautical and Space Sciences, Fall Conference*, Jeju, Korea (2018).
- **Dong Ho Lee**, Woohyuk Chang, and Jinku Buyn. “Discrete-event Modeling and Simulation of Autonomous Multi-UAV Mission Management.” *Avionics Systems Symposium Korea*, Yeosu, Korea (2018).

## Patent

Woohyuk Chang, **Dong Ho Lee**, and Hwanchol Jang. “Method and apparatus for optimization of unmanned vehicle mission allocation.” **KR102063851**, registered January 2020.
