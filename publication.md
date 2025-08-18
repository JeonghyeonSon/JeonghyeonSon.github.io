---
layout: page
title: Publications
permalink: /publication/
---

# 📚 Publications

## 📝 Work in Progress

{% assign wips = site.data.publications | where: "status", "wip" | sort: "year" | reverse %}
{% assign latest_wip = wips[0] %}
{% assign other_wips = wips | slice: 1, wips.size %}

- {{ latest_wip.authors }}. {{ latest_wip.year }}. {{ latest_wip.title }}. *{{ latest_wip.journal }}*{% if latest_wip.note %} ({{ latest_wip.note }}){% endif %}. <span id="toggle-wip" style="color: #007bff; cursor:pointer;">[Read more]</span>

<span id="other-wip-list" style="display:none;">
{% for pub in other_wips %}
- {{ pub.authors }}. {{ pub.year }}. {{ pub.title }}. *{{ pub.journal }}*{% if pub.note %} ({{ pub.note }}){% endif %}.
{% endfor %}
</span>

## 📔 Published

{% assign pubs = site.data.publications | where: "status", "published" | sort: "year" | reverse %}
{% for pub in pubs %}
- {{ pub.authors }}. {{ pub.year }}. {{ pub.title }}. *{{ pub.journal }}* {% if pub.volume %}{{ pub.volume }}{% endif %}{% if pub.pages %}:{{ pub.pages }}{% endif %}.
{% endfor %}

<script>
document.addEventListener('DOMContentLoaded', function() {
  var toggle = document.getElementById('toggle-wip');
  var list = document.getElementById('other-wip-list');
  if (toggle) {
    toggle.onclick = function() {
      if(list.style.display === 'none') {
        list.style.display = 'inline';
        toggle.textContent = '[Hide]';
      } else {
        list.style.display = 'none';
        toggle.textContent = '[Read more]';
      }
    }
  }
});
</script>
