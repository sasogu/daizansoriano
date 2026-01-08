---
layout: default
title: "Inicio"
---

<section class="hero">
  <div class="hero-inner">
    <div>
      <p class="eyebrow">Cada dia es un buen dia</p>
      <h1>{{ page.title }}</h1>
      <p class="lead">{{ site.description }}</p>
      <div class="hero-actions">
        <a class="pill is-filled" href="{{ '/archive/' | relative_url }}">Archivo</a>
        <a class="pill" href="{{ '/about/' | relative_url }}">Acerca de</a>
      </div>
    </div>
    <aside class="hero-card">
      <p class="hero-card__title">Ritual de lectura</p>
      <ul class="ritual-list">
        <li><span class="ritual-dot"></span>Respira hondo antes de abrir un texto.</li>
        <li><span class="ritual-dot"></span>Lee una nota y deja espacio para el eco.</li>
        <li><span class="ritual-dot"></span>Vuelve a una linea que quieras guardar.</li>
      </ul>
    </aside>
  </div>
</section>

<section class="post-list">
  <div class="section-heading">
    <p class="eyebrow">Ultimas notas</p>
    <h2>Lecturas recientes</h2>
  </div>
  <div class="post-grid">
    {% for post in site.posts %}
      <article class="post-card">
        <p class="post-meta">{{ post.date | date: "%d %b %Y" }}{% if post.categories %} · {{ post.categories | join: ", " }}{% endif %}</p>
        <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
        <p>{{ post.excerpt | strip_html | strip_newlines | truncate: 180 }}</p>
      </article>
    {% endfor %}
  </div>
</section>
