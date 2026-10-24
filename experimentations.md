---
title: Experimentations
permalink: /experimentations/
---

Things I've been building, breaking and learning from.

{% for post in site.posts %}
[{{ post.title }}]({{ post.url | relative_url }})  
{{ post.date | date: "%d %B %Y" }} — {{ post.summary }}

---
{% endfor %}