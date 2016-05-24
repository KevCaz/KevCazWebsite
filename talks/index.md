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
    {{ member.author }} ({{member.year}}) <b>{{ member.name }}</b> {{member.conf}}, {{member.city}}, {{member.country}}. &nbsp;
    {% if member.file %}
    <a href="{{ site.baseurl }}/talks/assets/{{ member.file }}"> <i class="fa fa-file-pdf-o"></i></a>
    {% endif %}
    {% if member.html %}
    <a href="{{ site.baseurl }}/talks/assets/{{ member.html }}"><i class="fa fa-html5" aria-hidden="true"></i></a>
    {% endif %}
  </li>
  <br>
{% endfor %}
</ul>
