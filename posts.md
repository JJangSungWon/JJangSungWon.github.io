---
layout: page
title: "Posts"
permalink: /posts/
main_nav: true
---

{% for category in site.categories %}
  {% capture cat %}{{ category | first }}{% endcapture %}

<details>
    <summary> <h2 id="{{cat}}">{{ cat |  }}</h2></summary>
        {% for desc in site.descriptions %}
    		{% if desc.cat == cat %}
        <p class="desc"><em>{{ desc.desc }}</em></p>
            {% endif %}
  		{% endfor %}
          <ul class="posts-list">
  {% for post in site.categories[cat] %}
    <li>
      <strong>
          <div markdown="1">
        <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </strong>
      <span class="post-date">- {{ post.date | date_to_long_string }}</span>
          </div>
    </li>
  {% endfor %}
  </ul>

  {% if forloop.last == false %}<hr>{% endif %}
{% endfor %}
<br>
   
</details>



