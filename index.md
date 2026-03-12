---
layout: default
title: "At-Tawahidiyya"
---

# At-Tawahidiyya

*A school of thought devoted to divine unity, scriptural coherence, and theological precision.*

---

## Foundations

These pages lay out the core metaphysical and theological axioms of At-Tawahidiyya.

<ul>
{% for page in site.foundations %}
  <li><a href="{{ page.url | relative_url }}">{{ page.title }}</a></li>
{% endfor %}
</ul>

{% assign foundation_posts = site.categories.foundation %}
{% if foundation_posts.size > 0 %}
<ul>
{% for post in foundation_posts %}
  <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a> &mdash; <small>{{ post.date | date: "%B %d, %Y" }}</small></li>
{% endfor %}
</ul>
{% endif %}

---

## Tawahidi Tafsir

Quranic interpretation through the lens of divine unity and internal scriptural coherence.

<ul>
{% for page in site.tafsir %}
  <li><a href="{{ page.url | relative_url }}">{{ page.title }}</a></li>
{% endfor %}
</ul>

{% assign tafsir_posts = site.categories.tafsir %}
{% if tafsir_posts.size > 0 %}
<ul>
{% for post in tafsir_posts %}
  <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a> &mdash; <small>{{ post.date | date: "%B %d, %Y" }}</small></li>
{% endfor %}
</ul>
{% endif %}

---

## Refutations

Systematic responses to theological objections, internal contradictions, and polemical challenges.

<ul>
{% for page in site.refutations %}
  <li><a href="{{ page.url | relative_url }}">{{ page.title }}</a></li>
{% endfor %}
</ul>

{% assign refutation_posts = site.categories.refutation %}
{% if refutation_posts.size > 0 %}
<ul>
{% for post in refutation_posts %}
  <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a> &mdash; <small>{{ post.date | date: "%B %d, %Y" }}</small></li>
{% endfor %}
</ul>
{% endif %}
