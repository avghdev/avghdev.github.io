---
layout: archive
permalink: /development/
---

<h2 class="center">Development</h2>
<p class="center"><em>an archive for all posts related to development</em></p>
<div class="tiles">
{% for post in site.categories.development %}
  {% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->

