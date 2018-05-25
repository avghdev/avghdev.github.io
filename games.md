---
layout: archive
permalink: /games/
---

<h2 class="center">Games</h2>
<p class="center"><em>an archive for all posts related to games</em></p>
<div class="tiles">
{% for post in site.categories.games %}
  {% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->
