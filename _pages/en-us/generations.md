---
page_id: generations
layout: page
permalink: /generations/
title: BCEM along the years
description: 
nav: false
nav_order: 
---

<div id="carouselExample" class="carousel slide" data-ride="carousel">
  <!-- Indicators -->
  <ol class="carousel-indicators">
    {% for pic in site.data.pictures_gens %}
      <li data-target="#carouselExample" data-slide-to="{{ forloop.index0 }}" class="{% if forloop.first %}active{% endif %}"></li>
    {% endfor %}
  </ol>

  <!-- Wrapper for slides -->
  <div class="carousel-inner">
    {% for pic in site.data.pictures_gens %}
      <div class="carousel-item {% if forloop.first %}active{% endif %}">
        <div class="text-center mb-2">
          <h3 style="font-size: 1.5rem; font-weight: bold;">{{ pic.year }}</h3>
        </div>
        <img src="{{ site.url }}{{ site.baseurl }}/assets/img/picpic/gens/{{ pic.image }}" class="d-block w-100 img-responsive" alt="{{ pic.year }}">
      </div>
    {% endfor %}
  </div>

  <!-- Controls -->
  <a class="carousel-control-prev" href="#carouselExample" role="button" data-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="sr-only">Previous</span>
  </a>
  <a class="carousel-control-next" href="#carouselExample" role="button" data-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="sr-only">Next</span>
  </a>
</div>

<p>&nbsp;</p>