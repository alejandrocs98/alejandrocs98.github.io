---
page_id: team
layout: page
permalink: /team/
title: Team
description: 
nav: true
nav_order: 1
---

{% assign sorted_team = site.team | sort: "started" %}
{% assign number_printed = 0 %}
{% for member in sorted_team %}

{% if member.started and member.ended == nil %}

{% assign mod = number_printed | modulo: 3 %}

{% if mod == 0 %}
<div class="row" style="margin-bottom: 10px;">
{% endif %}

{% include team_member.html member=member %}

{% assign number_printed = number_printed | plus: 1 %}

{% if mod == 2 %}
</div>
{% endif %}

{% endif %}

{% endfor %}


{% if mod != 2 %}
</div>
{% endif %}

--- 

# Past Members

<div class="row">
  {% assign sorted_team = site.team | sort: "ended" | reverse %}
  {% assign total_members = sorted_team.size %}
  
  {% for member in sorted_team %}
    {% if member.started and member.ended %}
      
      <!-- Determine the column size based on the total number of members
      and the current index in the loop. -->
      
      {% assign column_size = total_members | divided_by: 2 %}
      {% assign column_index = forloop.index0 | modulo: column_size %}
      
      {% if column_index == 0 %}
        <div class="col-md-6 mb-3">
      {% else %}
        <div class="col-md-6 mb-3">
      {% endif %}
      
      {% include former_team_member.html member=member %}
      </div>
    {% endif %}
  {% endfor %}
</div>

<p>&nbsp;</p>
