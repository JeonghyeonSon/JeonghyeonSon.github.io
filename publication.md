---
layout: page
title: Publications
permalink: /publication/
---



# 📝 Work in Progress

{% assign wips_submitted = site.data.publications | where: "status", "wip" | where: "note", "Submitted" | sort: "year" | reverse %}
{% assign wips_under_review = site.data.publications | where: "status", "wip" | where: "note", "Under review" | sort: "year" | reverse %}
{% assign wips_accepted = site.data.publications | where: "status", "wip" | where: "note", "Accepted" | sort: "year" | reverse %}
{% assign wips = wips_submitted | concat: wips_under_review | concat: wips_accepted %}
{% assign wip_total = wips | size %}

{% for pub in wips %}
- **{{ wip_total | minus: forloop.index0 }}.** {{ pub.authors }}. {{ pub.title }}. *{{ pub.journal }}*{% if pub.note %} ({{ pub.note }}){% endif %}.
{% endfor %}
---
# 📔 Peer-Reviewed Publications

{% assign pubs = site.data.publications | where: "status", "published" | sort: "year" | reverse %}
{% assign pub_total = pubs | size %}
{% for pub in pubs %}
- **{{ pub_total | minus: forloop.index0 }}.** {{ pub.authors }}. {{ pub.year }}. {{ pub.title }}. *{{ pub.journal }}*{% if pub.volume %} {{ pub.volume }}{% endif %}{% if pub.pages %}:{{ pub.pages }}.{% endif %}{% if pub.link %} [🔗]({{ pub.link }}){% endif %}
{% endfor %}
