---
layout: default
---

{% for post in site.posts %}
   <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
   <p>{{ post.image }}</p>
{% endfor %}
