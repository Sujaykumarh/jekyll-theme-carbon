---
title: Home
layout: default
active: home
---


{% if site.posts.size > 0 %}
# Posts
{% else %}
Nothing to show
{% endif %}
<br>    
<div class="posts row">
{% for post in site.posts %}
  <article class="post col col-12 col-xl-6">
    <h3><a href="{{ site.baseurl }}{{ post.url }}" class="post-url">{{ post.title }}</a></h3>
    <div class="post-date-tags">
      <span class="text-left post-date">{{ post.date | date_to_string }}</span>
      <span>
        <span class="tag-seprator">|</span>
        {% for tag in post.tags %}
          <a href="{{ site.baseurl }}/categories/#{{ tag | slugify }}" class="category-tag text-uppercase"><i class="fas fa-tag"></i>{{ tag }}</a>     
        {% endfor %}
      </span>
    </div>
    {% if post.image %}
      <img src="{{ post.image }}">
    {% endif %}
    <div class="entry text-justify">
      {{ post.excerpt | strip_html | strip_newlines | truncate: 156 }}
    </div>
    <div class="text-right">
      <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Read More . .</a>
    </div>
  </article>
{% endfor %}
</div>
