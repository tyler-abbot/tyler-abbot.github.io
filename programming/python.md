---
layout: archive
title: ""
date: 
modified:
excerpt:
image:
  feature: lorenz.jpg
  teaser: Jerry Ylilammi, ylilammi.com
  thumb:
ads: false
---

<div class="tiles">
{% for post in site.categories['programming']%}
    {% if post.subcategories == 'python'%}
	    {% include post-grid.html %}
    {% endif %}
{% endfor %}
</div><!-- /.tiles -->
