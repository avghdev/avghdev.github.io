---
layout: archive
permalink: /arts/
---

<h2 class="center">Arts</h2>
<p class="center"><em>an archive for all posts related to arts</em></p>
<div class="tiles">
{% for post in site.categories.art %}
  {% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->