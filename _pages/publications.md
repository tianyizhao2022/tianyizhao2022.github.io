---
layout: page
permalink: /publications/
title: Publications&Talks
description: 
nav: true
nav_order: 4
post-header: true
bibtypes:
  - bibquery: "@article"
    text: "Journal papers"  
  - bibquery: "@inproceedings"
    text: "Conference proceedings (peer-reviewed)"
  - bibquery: "@misc|@thesis"
    text: "Presentations at conferences"
---

{% for bibtype in page.bibtypes %}
  {% capture category_counter %}
  {% bibliography_count -f {{site.scholar.bibliography}} -q {{bibtype.bibquery}} %}
  {% endcapture %}

  <div style="counter-reset:bibitem {{ category_counter | plus:1 }}">
  <div class="publications">
  <h3 class="type">{{bibtype.text}}</h3>
    {% bibliography -f {{site.scholar.bibliography}} -q {{bibtype.bibquery}} %}
  </div>

{% endfor %}
