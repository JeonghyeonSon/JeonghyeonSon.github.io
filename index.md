---
layout: page
title: Home
permalink: /
---


## 🐷 Jeonghyeon Son [손 정현]
**Ph.D. Student in Animal Science (Swine Nutrition)**  

🐺 North Carolina State University  

📧 Email: [json7@ncsu.edu](mailto:json7@ncsu.edu)  
🔗 [Google Scholar](https://scholar.google.com/citations?user=FwQUdD4AAAAJ&hl=en&authuser=1) · 
[Scopus](https://www.scopus.com/authid/detail.uri?authorId=58131804100) · 
[LinkedIn](https://www.linkedin.com/in/jeonghyeon-son-107a10246/)

---

## 🎓 Education
- **PhD in Animal Science**  
  <a href="https://sungwookim.wordpress.ncsu.edu/kimlab/" style="color:#CC0000">North Carolina State University</a>, Raleigh, NC, Jan 2025–Present  

- **MS in Animal Science**  
  <a href="http://pig.konkuk.ac.kr/" style="color:#00693E">Konkuk University</a>, Seoul, South Korea, Aug 2023  

- **BS in Animal Science and Technology**  
  Konkuk University, Seoul, South Korea, Aug 2021  

---
## 🔬 Research Interests
- Precision nutrition in swine  
- Nutrient digestibility, availability, and requirement modeling  
- Nutritional interventions and microbiota analysis for intestinal health  


---
## 📚 Publications
**Latest Publications:**
{% assign pubs = site.data.publications | where: "status", "published" | reverse | sort: "year" | reverse %}
{% assign pub_total = pubs | size %}
{% for pub in pubs limit:3 %}
- **{{ pub_total | minus: forloop.index0 }}.** {{ pub.authors | replace: 'Son J', '<strong>Son J</strong>' }}. {{ pub.year }}. {{ pub.title }}. *{{ pub.journal }}*{% if pub.volume %} {{ pub.volume }}{% endif %}{% if pub.pages %}:{{ pub.pages }}.{% endif %}{% if pub.link %} [🔗]({{ pub.link }}){% endif %}
{% endfor %}

[**View All Publications →**](/publication/)







