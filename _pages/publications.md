---
layout: page
permalink: /publications/
title: publications
description: ...in reversed chronological order.
nav: true
---

<div class="publications">

{% for y in (2000..2100) reversed %}
  {% capture count %}{% bibliography_count -f papers -q @*[year={{y}}]* %}{% endcapture %}
  {% assign count= count|plus:0 %}
  {% if count > 0  %}
    <h2 class="year">{{y}}</h2>
    {% bibliography -f papers -q @*[year={{y}}]* %}  
  {% endif %}
{% endfor %}

</div>
