---
layout: default
---

# The Tawahidi Forge

## 🛡️ Active Refutations
{% for post in site.categories.refutation %}
### [{{ post.title }}]({{ post.url }})
*Solving logical knots in modern discourse.*
{% endfor %}

---

## 📖 Latest Tafsir
{% for post in site.categories.tafsir %}
### [{{ post.title }}]({{ post.url }})
{% endfor %}
