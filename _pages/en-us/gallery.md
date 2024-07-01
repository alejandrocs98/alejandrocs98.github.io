---
page_id: gallery
layout: page
permalink: /gallery/
title: Gallery
description: 
nav: false
nav_order: 
---

<div class="row">
  {% assign number_printed = 0 %}
  {% for pic in site.data.pictures_gal %}
    
    {% assign even_odd = number_printed | modulo: 2 %}
    
    <div class="col-sm-6 mb-4">
      <div class="rounded shadow p-0"> <!-- Removed p-3 class to remove padding -->
        <img src="{{ site.url }}{{ site.baseurl }}/assets/img/picpic/gallery/{{ pic.image }}" class="img-fluid rounded" alt="{{ pic.alt_text }}" style="width: 100%; height: auto; display: block;">
        <!-- Added inline styles to ensure full width and responsive behavior -->
      </div>
    </div>
    
    {% assign number_printed = number_printed | plus: 1 %}
    
    {% if even_odd == 1 or forloop.last %}
</div>
<div class="row">
    {% endif %}
    
  {% endfor %}
</div>

<p>&nbsp;</p>


