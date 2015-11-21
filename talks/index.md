---
layout: default
title: Talks
order: 2
---

## Oral Presentations

<ul>
{% for member in site.data.talks %}
  <!-- - {{ member.name }}    -->
  <li>
    {{ member.author }} ({{member.year}}) <b>{{ member.name }}</b> {{member.conf}}, {{member.city}}, {{member.country}}. &nbsp;<a href="{{ site.baseurl }}/talks/assets/{{ member.file }}"> <i class="fa fa-file-pdf-o"></i></a>
  </li>
  <br>
{% endfor %}
</ul>
