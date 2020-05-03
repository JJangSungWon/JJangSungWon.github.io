---
layout: page
title: "Posts"
permalink: /posts/
---
<div>
{% for category in site.categories %}
  <ul class="categories">
    {% for categoryName in category[0] % }
      {% if categoryName != null %}
        <li>
          <span><a href="/categories/{{ categoryName }}">
            {{ categoryName }}
          </a></span>
          <span class="count">{{ eachCategory[1].size }}</span>
        </li>
      {% endif %}
    {% endfor %}
  </ul>
{% endfor %}
</div>


