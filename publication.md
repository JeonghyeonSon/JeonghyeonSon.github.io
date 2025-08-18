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

<div id="other-wip-list" style="display:none;">
{% for pub in other_wips %}
- {{ pub.authors }}. {{ pub.year }}. {{ pub.title }}. *{{ pub.journal }}*{% if pub.note %} ({{ pub.note }}){% endif %}.
{% endfor %}
</div>

## 📔 Published

{% assign pubs = site.data.publications | where: "status", "published" | sort: "year" | reverse %}
{% for pub in pubs %}
- {{ pub.authors }}. {{ pub.year }}. {{ pub.title }}. *{{ pub.journal }}* {% if pub.volume %}{{ pub.volume }}{% endif %}{% if pub.pages %}:{{ pub.pages }}{% endif %}.
{% endfor %}

<style>
/* 들여쓰기 없애기: 마크다운 ul, ol, li 스타일 초기화 */
ul, ol {
    margin-left: 0;
    padding-left: 0;
}
li {
    margin-left: 0;
    padding-left: 0;
}
#other-wip-list {
    /* 마크다운 리스트 스타일로 나오게 하기 위해 block으로 설정 */
}
</style>

<script>
document.addEventListener('DOMContentLoaded', function() {
  var toggle = document.getElementById('toggle-wip');
  var list = document.getElementById('other-wip-list');
  if (toggle) {
    toggle.onclick = function() {
      list.style.display = (list.style.display === 'none') ? 'block' : 'none';
      toggle.textContent = (list.style.display === 'block') ? '[Hide]' : '[Read more]';
    }
  }
});
</script>
