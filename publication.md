---
layout: page
title: Publications
permalink: /publication/
---



# 📝 Work in Progress

{% assign wips_submitted = site.data.publications | where: "status", "wip" | where: "note", "Submitted" | reverse | sort: "year" | reverse %}
{% assign wips_under_review = site.data.publications | where: "status", "wip" | where: "note", "Under review" | reverse | sort: "year" | reverse %}
{% assign wips_accepted = site.data.publications | where: "status", "wip" | where: "note", "Accepted" | reverse | sort: "year" | reverse %}
{% assign wips = wips_submitted | concat: wips_under_review | concat: wips_accepted %}
{% assign wip_total = wips | size %}

{% if wip_total > 0 %}
{% for pub in wips %}
- **{{ wip_total | minus: forloop.index0 }}.** {{ pub.authors | replace: 'Son J', '<strong>Son J</strong>' }}. {{ pub.title }}. *{{ pub.journal }}*{% if pub.note %} ({{ pub.note }}){% endif %}.
{% endfor %}
{% else %}
*The pigsty is quiet for now 🐷*
{% endif %}
---
# 📔 Peer-Reviewed Publications

{% assign pubs = site.data.publications | where: "status", "published" | reverse | sort: "year" | reverse %}
{% assign pub_total = pubs | size %}
{% for pub in pubs %}
- **{{ pub_total | minus: forloop.index0 }}.** {{ pub.authors | replace: 'Son J', '<strong>Son J</strong>' }}. {{ pub.year }}. {{ pub.title }}. *{{ pub.journal }}*{% if pub.volume %} {{ pub.volume }}{% endif %}{% if pub.pages %}:{{ pub.pages }}.{% endif %}{% if pub.link %} [🔗]({{ pub.link }}){% endif %}
{% endfor %}
