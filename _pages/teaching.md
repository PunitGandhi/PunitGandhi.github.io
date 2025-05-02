---
layout: page
permalink: /teaching/
title: teaching
description: 
nav: true
nav_order: 4
display_categories: [CurrentSemester, VCU, OhioState, UCBerkeley]
horizontal: false
---
My goal as an instructor is to design a classroom environment that provides my students the opportunity to learn mathematical concepts using the same scientific process that I follow in my own research as an applied mathematician. This involves engaging students with challenging and open
ended problems, providing context through real-world applications and promoting a collaborative
environment where knowledge is shared through student interactions.

I also take a scientific approach to my teaching. I actively search for effective teaching strategies
that can help me develop as instructor and work to incorporate them in my classroom when there is
potential benefit for students. I then collect data in the form of student performance and feedback
to carefully gauge success, and make informed improvements through successive iteration. Finally,
I make any successful curriculum ideas and teaching strategies that I develop available to share
with other educators.

---

<!-- pages/teaching.md -->
<div class="courses">
{% if site.enable_course_categories and page.display_categories %}
  <!-- Display categorized courses -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_courses = site.courses | where: "category", category %}
  {% assign sorted_courses = categorized_courses | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for course in sorted_courses %}
      {% include courses_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for course in sorted_courses %}
      {% include courses.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_courses = site.courses | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for course in sorted_courses %}
      {% include courses_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for course in sorted_courses %}
      {% include courses.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
