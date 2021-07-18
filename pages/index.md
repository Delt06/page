---
layout: page
title: About
permalink: /
weight: 3
---

# **About Me**

Hi, I am **{{ site.author.name }}**,<br>

<div class="row justify-content-center align-items-center p-4">
  <div class="col-lg-4 col-md-6 text-center mt-4">

    <!-- Fine Circle Responsive Image -->
    <div id="container" class="my-2">
      <div id="dummy"></div>
      <div id="element">
        <img src="{{ site.author.image }}" alt="{{ site.title }}" class="circle-image wow animated zoomIn" data-wow-delay=".1s">
      </div>
    </div>
  </div>
</div>

I work with Unity since 2018. I am mostly interested in designing games' architecture and creating shaders.

<div class="row">
{% include about/skills.html title="Programming Skills" source=site.data.programming-skills %}
{% include about/skills.html title="Other Skills" source=site.data.other-skills %}
</div>

<div class="row">
{% include about/timeline.html %}
</div>