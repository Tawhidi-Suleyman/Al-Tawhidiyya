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

  <section class="index-column" id="foundations">
    <div class="column-header">
      <span class="column-numeral">I</span>
      <h2 class="column-title">The Pillars</h2>
      <p class="column-subtitle">Core metaphysical and theological axioms upon which the school rests.</p>
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
    {% assign fp = site.categories.foundation %}
    {% if fp.size > 0 %}
    <ul class="index-list">
      {% for post in fp %}
      <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a><time>{{ post.date | date: "%Y" }}</time></li>
      {% endfor %}
    </ul>
    {% endif %}
  </section>

  <section class="index-column" id="tafsir">
    <div class="column-header">
      <span class="column-numeral">II</span>
      <h2 class="column-title">The Library</h2>
      <p class="column-subtitle">Tawahidi Tafsir — Quranic interpretation through the lens of divine unity.</p>
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
    {% assign tp = site.categories.tafsir %}
    {% if tp.size > 0 %}
    <ul class="index-list">
      {% for post in tp %}
      <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a><time>{{ post.date | date: "%Y" }}</time></li>
      {% endfor %}
    </ul>
    {% endif %}
  </section>

  <section class="index-column" id="refutations">
    <div class="column-header">
      <span class="column-numeral">III</span>
      <h2 class="column-title">The Shield</h2>
      <p class="column-subtitle">Systematic responses to objections, polemics, and theological dilemmas.</p>
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
    {% assign rp = site.categories.refutation %}
    {% if rp.size > 0 %}
    <ul class="index-list">
      {% for post in rp %}
      <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a><time>{{ post.date | date: "%Y" }}</time></li>
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

<hr class="gold-rule" />

<!-- KEYWORD INDEX -->
<section class="keyword-index">
  <h2 class="section-heading">Keyword Index</h2>
  <div class="keyword-index-grid">
    {% assign all_tags = "" | split: "" %}
    {% for post in site.posts %}{% assign all_tags = all_tags | concat: post.tags %}{% endfor %}
    {% for doc in site.foundations %}{% assign all_tags = all_tags | concat: doc.tags %}{% endfor %}
    {% for doc in site.tafsir %}{% assign all_tags = all_tags | concat: doc.tags %}{% endfor %}
    {% for doc in site.refutations %}{% assign all_tags = all_tags | concat: doc.tags %}{% endfor %}
    {% assign all_tags = all_tags | uniq | sort %}
    {% for tag in all_tags %}
      <a href="{{ '/tags/' | append: tag | downcase | replace: ' ', '-' | relative_url }}" class="tag-pill">{{ tag }}</a>
    {% endfor %}
  </div>
</section>
