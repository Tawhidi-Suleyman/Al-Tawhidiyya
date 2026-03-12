---
layout: default
title: "The Master Index"
---

<div class="index-header">
  <h1 class="index-title">The Master Index</h1>
  <p class="index-epigraph">
    <em>"There is no god but God — and from that single axiom, all else follows."</em>
  </p>
</div>

<hr class="gold-rule index-rule" />

<div class="master-index">

  <!-- COLUMN I: THE PILLARS -->
  <section class="index-column" id="foundations">
    <div class="column-header">
      <span class="column-numeral">I</span>
      <h2 class="column-title">The Pillars</h2>
      <p class="column-subtitle">Foundations of Tawahidi metaphysics and core axioms upon which the school rests.</p>
    </div>
    <hr class="gold-rule" />
    <ul class="index-list">
      {% for doc in site.foundations %}
      <li>
        <a href="{{ doc.url | relative_url }}">{{ doc.title }}</a>
        {% if doc.excerpt %}<span class="entry-excerpt">{{ doc.excerpt | strip_html | truncate: 80 }}</span>{% endif %}
      </li>
      {% else %}
      <li class="empty-notice">No foundational texts yet archived.</li>
      {% endfor %}
    </ul>
    {% assign foundation_posts = site.categories.foundation %}
    {% if foundation_posts.size > 0 %}
    <ul class="index-list">
      {% for post in foundation_posts %}
      <li>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        <time>{{ post.date | date: "%Y" }}</time>
      </li>
      {% endfor %}
    </ul>
    {% endif %}
  </section>

  <!-- COLUMN II: THE LIBRARY -->
  <section class="index-column" id="tafsir">
    <div class="column-header">
      <span class="column-numeral">II</span>
      <h2 class="column-title">The Library</h2>
      <p class="column-subtitle">Tawahidi Tafsir — Quranic interpretation through the lens of divine unity and logical coherence.</p>
    </div>
    <hr class="gold-rule" />
    <ul class="index-list">
      {% for doc in site.tafsir %}
      <li>
        <a href="{{ doc.url | relative_url }}">{{ doc.title }}</a>
        {% if doc.excerpt %}<span class="entry-excerpt">{{ doc.excerpt | strip_html | truncate: 80 }}</span>{% endif %}
      </li>
      {% else %}
      <li class="empty-notice">No tafsir texts yet archived.</li>
      {% endfor %}
    </ul>
    {% assign tafsir_posts = site.categories.tafsir %}
    {% if tafsir_posts.size > 0 %}
    <ul class="index-list">
      {% for post in tafsir_posts %}
      <li>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        <time>{{ post.date | date: "%Y" }}</time>
      </li>
      {% endfor %}
    </ul>
    {% endif %}
  </section>

  <!-- COLUMN III: THE SHIELD -->
  <section class="index-column" id="refutations">
    <div class="column-header">
      <span class="column-numeral">III</span>
      <h2 class="column-title">The Shield</h2>
      <p class="column-subtitle">Refutations — systematic responses to objections, polemics, and theological dilemmas.</p>
    </div>
    <hr class="gold-rule" />
    <ul class="index-list">
      {% for doc in site.refutations %}
      <li>
        <a href="{{ doc.url | relative_url }}">{{ doc.title }}</a>
        {% if doc.excerpt %}<span class="entry-excerpt">{{ doc.excerpt | strip_html | truncate: 80 }}</span>{% endif %}
      </li>
      {% else %}
      <li class="empty-notice">No refutations yet archived.</li>
      {% endfor %}
    </ul>
    {% assign refutation_posts = site.categories.refutation %}
    {% if refutation_posts.size > 0 %}
    <ul class="index-list">
      {% for post in refutation_posts %}
      <li>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        <time>{{ post.date | date: "%Y" }}</time>
      </li>
      {% endfor %}
    </ul>
    {% endif %}
  </section>

</div>

<hr class="gold-rule" />

<!-- RECENT WRITINGS -->
<section class="recent-writings">
  <h2 class="section-heading">Recent Writings</h2>
  <ul class="index-list recent-list">
    {% for post in site.posts limit:5 %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%d %B %Y" }}</time>
      {% if post.tags %}
        <span class="inline-tags">
          {% for tag in post.tags %}<span class="tag-inline">{{ tag }}</span>{% endfor %}
        </span>
      {% endif %}
    </li>
    {% endfor %}
  </ul>
</section>
