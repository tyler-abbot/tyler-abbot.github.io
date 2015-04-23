---
layout: archive
title: ""
date: 
modified:
excerpt:
image:
  feature: lorenz.jpg
  credit:  Jerry Ylilammi, ylilammi.com
  teaser:
  thumb:
ads: false
---

<div class="tiles">
{% for post in site.categories['programming']%}
    {% if post.subcategories == 'tips' %}
	    {% include post-grid.html %}
    {% endif %}
{% endfor %}
</div><!-- /.tiles -->
