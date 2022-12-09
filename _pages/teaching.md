---
layout: page
permalink: /teaching/
title: Teaching
description: Below you will find the material of some courses, as well as the full list of my teaching so far
nav: true
nav_order: 3
horizontal: false
---

## Courses Material

<!-- pages/teaching.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.courses | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.courses | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>

## Courses List
<!-- Display courses list -->
<div class="post">   

          <article>
            <div class="cv">
              {% for entry in site.data.courses %}
                <div class="card mt-3 p-3">
                  <h3 class="card-title font-weight-medium">{{ entry.title }}</h3>
                  <div>
                  {% if entry.type == "list" %}
                    {% include cv/list.html %}
                  {% elsif entry.type == "map" %}
                    {% include cv/map.html %}
                  {% elsif entry.type == "nested_list" %}
                    {% include cv/nested_list.html %}
                  {% elsif entry.type == "time_table" %}
                   {% include cv/time_table.html %}
                  {% else %}
                    {{ entry.contents }}
                  {% endif %}
                  </div>
                </div>
              {% endfor %}
              </div>
          </article>

</div>
