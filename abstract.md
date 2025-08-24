---
layout: page
title: Abstracts
permalink: /abstract/
---



# 📋 Conference Abstracts

{% assign abstracts = site.data.abstracts | sort: "year" | reverse %}
{% assign abstract_total = abstracts | size %}
{% for abstract in abstracts %}
- **{{ abstract_total | minus: forloop.index0 }}.** {{ abstract.authors | replace: 'Son J', '<strong>Son J</strong>' }}. {{ abstract.year }}. {{ abstract.title }}. *{{ abstract.conference }}*{% if abstract.link and abstract.link != "not yet" %} [🔗]({{ abstract.link }}){% endif %}.
{% endfor %}

---