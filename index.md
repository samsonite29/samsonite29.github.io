---
layout: page
---

<div style="display:flex; align-items:center; gap:1.5rem; margin-bottom:2rem;">
  <img src="{{ '/assets/images/me.jpeg' | relative_url }}" alt="Samson" style="width:90px; height:90px; border-radius:50%; object-fit:cover;">
  <h1 style="margin:0;">Hello, my name is Samson</h1>
</div>

I'm a backend and platform engineer focused on building distributed services and the cloud infrastructure they run on.

Currently I work at LexisNexis Risk Solutions. I work with AWS, Kubernetes (EKS), Terraform, FluxCD and GitHub Actions, and I've got a backend background in Python, .NET and TypeScript.

You can find me on [GitHub](https://github.com/samsonite29) and [LinkedIn](https://linkedin.com/in/oyedefunbi), or [send me an email](mailto:you@example.com).

## Recent Experimentations

Things I've been building, breaking and learning from.

{% for post in site.posts limit:3 %}
[{{ post.title }}]({{ post.url | relative_url }})  
{{ post.date | date: "%d %B %Y" }} — {{ post.summary }}

---
{% endfor %}

[See all experimentations →]({{ '/experimentations/' | relative_url }})