---
layout: default
permalink: /
title: "a home page"
---
<div class="page-lead" style="background-image:url(images/feature.jpg)">
      <div class="page-lead-content">
        <h1>underdeveloped</h1>
        <h2>a home page</h2>
      </div><!-- /.page-lead-content -->
</div>

<div class="page-wrapper">
    <div id="main" role="main" class="wrap">
        <div class="page-title">
            <h3>welcome to 'underdeveloped' - <em>always in progress</em></h3>
        </div>
        <div class ="page-content">
            <p>I decided to make a personal website. I'm a pretty simple guy, so it's a pretty simple website. You'll find my general musings regarding life here. I'll mainly be writing about development stuff - but occasionally I'll diverge from that mantra. I hope to constantly improve as I go.</p>
            <blockquote>This website is - as the name might imply - a perpetual work-in-progress</blockquote>
        </div>
        <hr>
        <h4>latest posts</h4>
        <div class="tiles">
        {% for post in site.posts %}
          {% include post-grid.html %}
        {% endfor %}
        </div>
    </div>
    
</div>

