---
layout: page
title: "Posts"
permalink: /posts/
main_nav: true

---

{% for category in site.categories %}
  {% capture cat %}{{ category | first }}{% endcapture %}

```markdown
<details>
<summary>접기/펼치기 버튼</summary>
<div markdown="1">

|제목|내용|
|--|--|
|1|1|
|2|10|

</div>
</details>
```

  <h2 id="{{cat}}">{{ cat |  }}</h2>

  {% for desc in site.descriptions %}
    {% if desc.cat == cat %}

      <p class="desc"><em>{{ desc.desc }}</em></p>

​    {% endif %}
  {% endfor %}

  <ul class="posts-list">
  {% for post in site.categories[cat] %}
    <li>
      <strong>
        <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </strong>
      <span class="post-date">- {{ post.date | date_to_long_string }}</span>
    </li>
  {% endfor %}
  </ul>

  {% if forloop.last == false %}<hr>{% endif %}
{% endfor %}
<br>

