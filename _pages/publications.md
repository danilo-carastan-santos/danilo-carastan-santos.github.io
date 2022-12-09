---
layout: page
permalink: /publications/
title: Publications
description: 'In agreement with the research teams I worked with, my publication
strategy value high-quality conferences (e.g., Core A-ranking
conferences such as SC and CCgrid) and journals (e.g., Nature
Communications, FGCS, CCPE). As a junior researcher, I tend to
prioritize conference publications over journals since conferences can
leverage me to establish new scientific connections and collaborations.<br/>
When I work with undergraduate and Masters students, I also seek to
foster their interaction with the research community and reward their
research work by accepting publishing in B-ranking international
conferences (e.g., ISCC) and regional conferences and workshops (e.g.,
CARLA and WSCAD). In this case, the goal is maximizing the students
research experience, giving them the advantage to reach higher research
positions, notably by acquiring a PhD student position.<br/>
In working with specific research teams, the publications list the
authors alphabetically.'
years: [Jounal articles, International conference papers, Regional conferences and workshops]
nav: true
nav_order: 1
---
<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year" style="color:black">{{y}}</h2>
  <br/><br/>
  {% bibliography -f papers -q @*[pubtype={{y}}]* %}
{% endfor %}

</div>
