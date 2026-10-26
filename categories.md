---
layout: default
title: 전체 글
permalink: /categories/
---

<div class="archive-intro">
  <p class="dashboard-eyebrow">ARCHIVE</p>
  <h1>전체 글</h1>
  <p>지금까지 기록한 글을 카테고리별로 모았습니다.</p>
</div>

{% if site.categories.size > 0 %}
  {% for category in site.categories %}
    {% assign category_slug = category[0] | slugify %}
    <section class="archive-category" id="{{ category_slug }}">
      <div class="section-heading-row">
        <h2>{{ category[0] }}</h2>
        <span class="archive-count">{{ category[1].size }}개의 글</span>
      </div>
      <div class="post-list dashboard-post-list">
        {% for post in category[1] %}
          <article class="dashboard-post-card">
            <div class="post-card-meta"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: site.minima.date_format }}</time></div>
            <h3><a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a></h3>
            {% if post.excerpt %}<div class="post-excerpt">{{ post.excerpt | strip_html | truncate: 140 }}</div>{% endif %}
          </article>
        {% endfor %}
      </div>
    </section>
  {% endfor %}
{% else %}
  <div class="empty-state archive-empty">
    <div class="empty-state-icon" aria-hidden="true">✦</div>
    <p class="empty-state-kicker">아카이브</p>
    <h3>아직 발행된 글이 없습니다</h3>
    <p>새 글을 쓰고 카테고리를 지정하면 이곳에서 찾아볼 수 있어요.</p>
  </div>
{% endif %}

