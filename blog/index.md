---
layout: default
title: Blog
permalink: /blog/
---

<style>
  .categories-nav {
    text-align: center;
    margin-bottom: 60px;
    padding-bottom: 30px;
    border-bottom: 1px solid #eaeaea;
  }
  .categories-nav h3 {
    font-size: 1.2rem;
    color: #86655d;
    margin-bottom: 20px;
    text-transform: uppercase;
    letter-spacing: 1px;
  }
  .cat-tags {
    display: flex;
    justify-content: center;
    gap: 15px;
    flex-wrap: wrap;
  }
  .cat-btn {
    background-color: #fff0e9; /* Il tuo colore crema */
    color: #3a3a3a;
    padding: 10px 20px;
    border-radius: 50px; /* Pill shape */
    text-decoration: none;
    font-weight: bold;
    font-size: 0.9rem;
    transition: all 0.3s ease;
    border: 1px solid transparent;
  }
  .cat-btn:hover {
    background-color: #ffb4a2; /* Il tuo colore salmone */
    color: white;
    transform: translateY(-2px);
    text-decoration: none;
  }
</style>

<div class="blog-index-wrapper">

  <h1>I miei pensieri</h1>

  <div class="categories-nav">
    <h3>Esplora per argomenti</h3>
    <div class="cat-tags">
      {% for category in site.categories %}
        {% capture category_name %}{{ category | first }}{% endcapture %}
        <a href="/{{ category_name | downcase }}/" class="cat-btn">
          {{ category_name }} <small>({{ category | last | size }})</small>
        </a>
      {% endfor %}
    </div>
  </div>

  <ul class="post-list">
    {% for post in site.posts %}
      <li>
        <span class="post-meta">{{ post.date | date: "%-d %B %Y" }}</span>
        
        <h3>
          <a class="post-link" href="{{ post.url | relative_url }}">
            {{ post.title | escape }}
          </a>
        </h3>

        <div style="margin-bottom: 10px; font-size: 0.85rem; color: #86655d;">
           {% for cat in post.categories %}
             <span style="background: #eee; padding: 2px 8px; border-radius: 4px; margin-right: 5px;">#{{ cat }}</span>
           {% endfor %}
        </div>

        {% if post.excerpt %}
          <p>{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
        {% endif %}
        
        <a href="{{ post.url | relative_url }}" class="btn" style="padding: 10px 20px; font-size: 0.7rem;">Leggi</a>
      </li>
    {% endfor %}
  </ul>

</div>