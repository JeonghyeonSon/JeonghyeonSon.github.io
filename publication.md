---
layout: page
title: Publications
permalink: /publication/
---

# 📚 Publications

<button id="wip-toggle" style="margin-bottom:10px;">📝 Show/Hide Work in Progress</button>
<div id="wip-list">
{% assign wips = site.data.publications | where: "status", "wip" | sort: "year" | reverse %}
{% for pub in wips %}
- {{ pub.authors }}. {{ pub.year }}. {{ pub.title }}. *{{ pub.journal }}*{% if pub.note %} ({{ pub.note }}){% endif %}.
{% endfor %}
</div>

## 📔 Published

{% assign pubs = site.data.publications | where: "status", "published" | sort: "year" | reverse %}
{% for pub in pubs %}
- {{ pub.authors }}. {{ pub.year }}. {{ pub.title }}. *{{ pub.journal }}* {% if pub.volume %}{{ pub.volume }}{% endif %}{% if pub.pages %}:{{ pub.pages }}{% endif %}.
{% endfor %}

<script>
document.addEventListener('DOMContentLoaded', function() {
  var btn = document.getElementById('wip-toggle');
  var list = document.getElementById('wip-list');
  list.style.display = 'none';
  btn.onclick = function() {
    list.style.display = (list.style.display === 'none') ? 'block' : 'none';
  }
});
</script>
