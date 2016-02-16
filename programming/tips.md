---
layout: archive
title: ""
date:
modified:
excerpt:
image:
  feature: lorenz_1.jpg
  credit:  Jerry Ylilammi, ylilammi.com
  teaser:
  thumb:
ads: false
---

<div class="tiles">
{% for post in site.categories['programming'] reversed %}
    {% if post.subcategories == 'tips' %}
	    {% include post-grid.html %}
    {% endif %}
{% endfor %}
</div><!-- /.tiles -->

<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

  ga('create', 'UA-62675051-1', 'auto');
  ga('send', 'pageview');

</script>
