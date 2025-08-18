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
<span id="toggle-wip" style="color: #007bff; cursor:pointer;">[Read more]</span>

<div id="other-wip-list" class="hidden-list">
{% for pub in other_wips %}
{% assign wip_num = wip_total | minus: forloop.index %}
- **{{ wip_num }}.** {{ pub.authors }}. {{ pub.year }}. {{ pub.title }}. *{{ pub.journal }}*{% if pub.note %} ({{ pub.note }}){% endif %}.
{% endfor %}
</div>

## 📔 Published

{% assign pubs = site.data.publications | where: "status", "published" | sort: "year" | reverse %}
{% assign pub_total = pubs | size %}
{% assign pub_num = pub_total %}
{% for pub in pubs %}
- **{{ pub_num | minus: forloop.index0 }}.** {{ pub.authors }}. {{ pub.year }}. {{ pub.title }}. *{{ pub.journal }}* {% if pub.volume %}{{ pub.volume }}{% endif %}{% if pub.pages %}:{{ pub.pages }}{% endif %}.
{% endfor %}

<style>
.hidden-list {
  display: none;
}
</style>
<script>
document.addEventListener('DOMContentLoaded', function() {
  var toggle = document.getElementById('toggle-wip');
  var list = document.getElementById('other-wip-list');
  if (toggle && list) {
    toggle.onclick = function() {
      if(list.style.display === 'none' || list.classList.contains('hidden-list')) {
        list.style.display = 'block';
        list.classList.remove('hidden-list');
        toggle.textContent = '[Hide]';
      } else {
        list.style.display = 'none';
        list.classList.add('hidden-list');
        toggle.textContent = '[Read more]';
      }
    }
  }
});
</script>
