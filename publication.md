---
layout: page
title: Publications
permalink: /publication/
---

# 📚 Publications

## 📝 Work in Progress

{% assign wips = site.data.publications | where: "status", "wip" | sort: "year" | reverse %}
{% assign wip_total = wips | size %}
{% assign latest_wip = wips[0] %}
{% assign other_wips = wips | slice: 1, wip_total %}

{% assign wip_num = wip_total %}
- **{{ wip_num }}.** {{ latest_wip.authors }}. {{ latest_wip.year }}. {{ latest_wip.title }}. *{{ latest_wip.journal }}*{% if latest_wip.note %} ({{ latest_wip.note }}){% endif %}.

<details>
  <summary style="color: #007bff; cursor:pointer;">[Read more]</summary>
{% for pub in other_wips %}
- **{{ wip_num | minus: forloop.index }}.** {{ pub.authors }}. {{ pub.year }}. {{ pub.title }}. *{{ pub.journal }}*{% if pub.note %} ({{ pub.note }}){% endif %}.
{% endfor %}
</details>

## 📔 Published

{% assign pubs = site.data.publications | where: "status", "published" | sort: "year" | reverse %}
{% assign pub_total = pubs | size %}
{% for pub in pubs %}
- **{{ pub_total | minus: forloop.index0 }}.** {{ pub.authors }}. {{ pub.year }}. {{ pub.title }}. *{{ pub.journal }}* {% if pub.volume %}{{ pub.volume }}{% endif %}{% if pub.pages %}:{{ pub.pages }}{% endif %}.
{% endfor %}
