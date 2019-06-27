---
title: Categories
layout: page
---

<div class="blog list">
    <ul>
    {% for category in site.categories %}
        <li><a name="{{ category | first }}" href="{{site.baseurl}}/category/{{ category | first }}">{{ category | first }}</a>
          <ul>
          {% for post in category.last %}
            <li><a href="{{site.baseurl}}/{{ post.url }}">{{ post.title }}</a></li>
          {% endfor %}
          </ul>
        </li>
    {% endfor %}    
    </ul>

</div>
