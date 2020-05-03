---
layout: page
title: "Posts"
permalink: /posts/
main_nav: true
---

<div>
    {% for category in site.categories %}
     <ul class ="categories">
     	{% for categoryName in category[0] %}
         {% if categoryName != null %}
         	<li>
                <span><a href="/posts/{{ categoryName }}">
                    {{ categoryName }}
                </a></span>
                <span class="count">{{ category[1].size }}</span>
         	</li>
         {% endif %}
    	{% endfor %}
    </ul>
   {% endfor %}
</div>

