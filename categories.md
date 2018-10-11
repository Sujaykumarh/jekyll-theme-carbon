---
title: Categories
layout: default
active: categories
---

## Tags

<div class="row" id="category-tags">
    {% for tag in site.tags %}
        {% capture tag_name %}{{ tag | first }}{% endcapture %}
        {% assign tag_name = tag_name | slugize %}
        <a href="#{{ tag[0] | slugify }}" class="category-tag text-uppercase"><i class="fas fa-tag"></i>{{ tag_name }}</a>
    {% endfor %}
</div>
<hr>

{% for tag in site.tags %}
<div style="margin-bottom: 25px">
    {% capture tag_name %}{{ tag | first }}{% endcapture %}
    {% assign tag_name = tag_name | slugize %}
    <h5 id="#{{ tag[0] | slugify }}" class="text-uppercase">{{ tag_name }}</h5>
    <ul class="category-items">
        {% for post in tag[1] %}
        <a href="{{ site.baseurl }}{{ post.url }}">
            <li class="category-item">
                {{ post.title }} - 
                <span class="text-monospace">{{ post.date | date_to_string }}</span>
            </li>
        </a>
        {% endfor %}
    </ul>
</div>
{% endfor %}