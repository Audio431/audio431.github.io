---
layout: default
---

<h2 class="section-heading">Projects</h2>

<div class="card-grid">
{% for project in site.data.projects %}
  <div class="card">
    <h3 class="card-title"><a href="{{ project.url }}" target="_blank" rel="noopener">{{ project.name }}</a></h3>
    <p class="card-description">{{ project.description }}</p>
    <div class="card-tags">
      {% for tag in project.tags %}
      <span class="card-tag">{{ tag }}</span>
      {% endfor %}
    </div>
  </div>
{% endfor %}
</div>

<div class="reveal">
<h2 class="section-heading">Blog</h2>

{% if site.posts.size > 0 %}
<div class="card-grid">
{% for post in site.posts %}
  <div class="card blog-card">
    <span class="card-date">{{ post.date | date: "%b %d, %Y" }}</span>
    <h3 class="card-title"><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></h3>
    <p class="card-description">{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
  </div>
{% endfor %}
</div>
{% else %}
<p class="empty-state">No posts yet.</p>
{% endif %}
</div>
