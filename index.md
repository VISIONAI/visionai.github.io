---
layout: page
title: vision.ai
tagline: Let our vision empower your vision.
---
{% include JB/setup %}

<ul class="posts">
  {% for post in site.posts %}
    <li>
      <div>
        <h3 style="margin-bottom:0px">
        <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a>
        </h3>
        &raquo; <span>{{ post.date | date_to_string }}</span> 
      </div>
      <div>
        <div class="well">
          {{ post.content | strip_html | truncatewords:75}}
        </div>
        <div>
          <a href="{{ post.url }}">Read more...</a><br><br>
        </div>
      </div>
    </li>
  {% endfor %}
</ul>


