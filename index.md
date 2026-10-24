---
layout: page
---

<div style="display:flex; align-items:center; gap:1.5rem; margin-bottom:2rem;">
  <img src="{{ '/assets/images/boy.jpeg' | relative_url }}" alt="Samson" style="width:90px; height:90px; border-radius:50%; object-fit:cover;">
  <h1 style="margin:0;">Hello, my name is Samson</h1>
</div>

I'm Software Engineer focused on the design of scalable, resilient, and event-driven distributed systems. Experienced in cloud-native architectures, platform engineering with a passion for building robust data systems at scale

Currently I work at LexisNexis Risk Solutions as a Platform Engineer. I work with AWS, Kubernetes, Terraform, Mongodb and more. I focus on keeping the data platforms reliable, correct and secure.

You can find me on [GitHub](https://github.com/samsonite29) and [LinkedIn](https://linkedin.com/in/oyedefunbi).

## Recent Experimentations

Things I've been building, breaking and learning from.

{% for post in site.posts limit:3 %}
[{{ post.title }}]({{ post.url | relative_url }})  
{{ post.date | date: "%d %B %Y" }} — {{ post.summary }}

---
{% endfor %}

[See all experimentations →]({{ '/experimentations/' | relative_url }})