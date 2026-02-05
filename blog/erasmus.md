---
layout: default
title: Erasmus
permalink: /erasmus/
---

<div class="blog-index-wrapper">
  
  <h1>Diari dall'Erasmus</h1>
  
  <ul class="post-list">
    {% assign erasmus_posts = site.categories.erasmus %}

    {% for post in erasmus_posts %}
      <li>
        <span class="post-meta">{{ post.date | date: "%-d %B %Y" }}</span>
        <h3>
          <a class="post-link" href="{{ post.url | relative_url }}">
            {{ post.title | escape }}
          </a>
        </h3>
        
        {% if post.excerpt %}
          <p>{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
        {% endif %}
        
        <a href="{{ post.url | relative_url }}" class="btn" style="padding: 10px 20px; font-size: 0.7rem;">Leggi Articolo</a>
      </li>
    {% else %}
      <div style="text-align: center; padding: 40px;">
        <p style="color: #86655d; font-size: 1.2rem;">
          Non ci sono ancora articoli in questa sezione.
        </p>
        <p style="font-size: 0.9rem;">
          <em>Suggerimento: Controlla di aver scritto <code>categories: [erasmus]</code> nell'intestazione dei tuoi post.</em>
        </p>
      </div>
    {% endfor %}
  </ul>

</div>