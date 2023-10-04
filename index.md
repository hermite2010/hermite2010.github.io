---
layout: default
---

{% for post in site.posts %}
   <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
   {%- if post.image -%}
          <img src="{{- post.image | relative_url -}}" alt="">
        {%- endif -%}
{% endfor %}
