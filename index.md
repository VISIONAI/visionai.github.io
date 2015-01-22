---
layout: page
title: blog.vision.ai
tagline: Let our vision empower your vision
---
{% include JB/setup %}

<ul class="posts">
  {% for post in site.posts %}
    <li>
      <div>
        <h3 style="margin-bottom:0px">
        <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a>
        </h3>
        &raquo; <span>{{ post.date | date: '%B %d, %Y'}}</span> 
      </div>
      <div class="container">
        <div class="row">
          {% if post.image != nil %}
          <div class="col-md-2 col-lg-2">
              <img src="/images/{{post.image}}" style="width:80%">
          
          </div>
          <div class="col-md-8 col-lg-8">
          {% else %}
          <div class="col-md-12">
          {% endif %}
            <div>
              {{ post.content | strip_html | truncatewords:40}}
            </div>
            <div>
              <a href="{{ post.url }}">Read more...</a><br><br>
            </div>
          </div>
        </div>
      </div>
    </li>
  {% endfor %}
</ul>


