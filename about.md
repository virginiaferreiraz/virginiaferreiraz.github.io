---
layout: default
---
<ul class="post-list">
  {% for post in site.posts %}
  <li>
    <a class="post-card" href="{{ post.url | relative_url }}">
      <div class="post-card__meta">
        {% include moon.html category=post.category %}
        <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%d de %B de %Y" }}</time>
      </div>
      <h2 class="post-card__title">{{ post.title }}</h2>
      <p class="post-card__excerpt">{{ post.excerpt | strip_html | truncatewords: 28 }}</p>
    </a>
  </li>
  {% endfor %}
</ul>

{% if site.posts.size == 0 %}
<p style="color: var(--color-text-muted); text-align:center; padding: 60px 0;">
  Nenhum post ainda. Crie um arquivo em <code>_posts/</code> para começar — veja o README.
</p>
{% endif %}
