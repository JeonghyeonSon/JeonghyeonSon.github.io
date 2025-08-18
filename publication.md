---
layout: page
title: Publications
permalink: /publication/
---

# 📚 Publications

<details>
<summary>📝 Work in Progress</summary>

{% assign wips = site.data.publications | where: "status", "wip" | sort: "year" | reverse %}
{% for pub in wips %}
- {{ pub.authors }}. {{ pub.year }}. {{ pub.title }}. *{{ pub.journal }}*{% if pub.note %} ({{ pub.note }}){% endif %}.
{% endfor %}

</details>

## 📔 Published

{% assign pubs = site.data.publications | where: "status", "published" | sort: "year" | reverse %}
{% for pub in pubs %}
- {{ pub.authors }}. {{ pub.year }}. {{ pub.title }}. *{{ pub.journal }}* {% if pub.volume %}{{ pub.volume }}{% endif %}{% if pub.pages %}:{{ pub.pages }}{% endif %}.
{% endfor %}

