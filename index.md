## Active Refutations
{% for post in site.categories.refutation %}
### [{{ post.title }}]({{ post.url | relative_url }})
{% endfor %}

## Foundations
{% for page in site.foundations %}
### [{{ page.title }}]({{ page.url | relative_url }})
{% endfor %}
