---
layout: page
title: CIS 5650 - All Semesters
description: >
  Previous Semesters
hide_description: true
permalink: /previous-semesters/
---

{%- assign first_year = 2012 -%}
{%- assign latest_year = site.course_year | minus: 1 -%}
{%- assign span = latest_year | minus: first_year -%}
{%- for offset in (0..span) -%}
{%- assign year = latest_year | minus: offset -%}
{%- if year >= site.course_rename_year -%}{%- assign slug = "cis5650" -%}{%- else -%}{%- assign slug = "cis565" -%}{%- endif %}
### [Fall {{ year }}](https://{{ slug }}-fall-{{ year }}.github.io)
{% endfor %}