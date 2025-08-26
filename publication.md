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
- **{{ wip_total | minus: forloop.index0 }}.** {{ pub.authors | replace: 'Son J', '<strong>Son J</strong>' }}. {{ pub.title }}. *{{ pub.journal }}*{% if pub.note %} ({{ pub.note }}){% endif %}.
{% endfor %}
---
# 📔 Peer-Reviewed Publications

{% assign pubs_all = site.data.publications | where: "status", "published" %}
{% assign pub_total = pubs_all | size %}

{%- comment -%}
  그룹을 먼저 만들고, 그룹의 이름(=year)만 정렬/역순 처리
  → 그룹 내부 아이템 순서는 데이터 파일 순서 유지(=최신을 맨 위에 써두면 그대로 위)
{%- endcomment -%}
{% assign groups = pubs_all | group_by: "year" | sort: "name" | reverse %}

{%- assign count = pub_total -%}
{% for g in groups %}
  {%- for pub in g.items -%}
{{ count }}. {{ pub.authors }}. {{ pub.year }}. {{ pub.title }}. {{ pub.journal }}{% if pub.volume %} {{ pub.volume }}{% endif %}{% if pub.pages %}:{{ pub.pages }}.{% endif %}{% if pub.link %} [🔗]({{ pub.link }}){% endif %}
    {%- assign count = count | minus: 1 -%}
  {%- endfor -%}
{% endfor %}

