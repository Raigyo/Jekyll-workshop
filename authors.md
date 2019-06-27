---
title: Authors
layout: page
---

<div class="blog list">
  <ul>
  {% for member in site.data.members %}
    <li id="{{ member.name }}">
      <a href="https://github.com/{{ member.github }}">
        {{ member.name }}
      </a>
    </li>
    <ul>
      {% assign the_author=member.name %}
      {% for post in site.posts %}
        {% for author in post.author %}
          {% if author == the_author %}
          {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}

            <li class="post-meta"><a href="{{site.baseurl}}{{ post.url }}">{{ post.title }}</a> •  <time class="dt-published"> {{ post.date | date: date_format }}</time>
            </li>
          {% endif %}
        {% endfor %}
      {% endfor %}
    </ul>
  {% endfor %}
  </ul>
</div>
