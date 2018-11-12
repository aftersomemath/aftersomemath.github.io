---
layout: page
permalink: /publications/
title: publications
description:
yearspapers: [2018, 2017]
yearspres:   [2018, 2017]
yearsrep:    [2018]
---

{% for y in page.yearspapers %}
  <h3 class="year">{{y}}</h3>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

# presentations
{% for y in page.yearspres %}
  <h3 class="year">{{y}}</h3>
  {% bibliography -f presentations -q @*[year={{y}}]* %}
{% endfor %}

# technical reports
{% for y in page.yearsrep %}
  <h3 class="year">{{y}}</h3>
  {% bibliography -f technicalreports -q @*[year={{y}}]* %}
{% endfor %}
