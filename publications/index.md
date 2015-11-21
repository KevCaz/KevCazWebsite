---
title: Publications
layout: default
order: 1
---

## Academic Contributions

<ul>
{% for member in site.data.publi.references %}
  <li>
  {% assign sza = member.author | size  %}
  {% assign count = 0 %}
  {% for auteur in member.author %}
    {% assign count = count | plus: 1 %}
    {{auteur.family}}
    {% assign words = auteur.given | split: ' ' %}
    {% if count == sza %}
      {% for word in words %} {{ word | slice: 0 }}. {% endfor %}
    {% else %}
      {% for word in words %} {{ word | slice: 0 }}.{% endfor %},
    {% endif %}
  {% endfor %}

  ({{member.issued.date-parts[0][0]}})
  {{ coucou }}
   <a href="{{member.URL}}">{{member.title}}</a>.
  <i>{{member.container-title}}</i>,

  {% if member.volume %}
    <b>{{ member.volume }}</b>, {{ member.page }}
  {% else %}
    <b>DOI: {{ member.DOI }}</b>
  {% endif %}

  &nbsp;
  <a href="mailto:kevin.cazelles@um2.fr?subject=Request: {{member.title}}&body=Dear Kevin, %0D%0A Could you please send me your paper entitled '{{member.title}}'?">
  <i class="fa fa-envelope"></i></a>
  </li>
  <br>

{% endfor %}
</ul>



<!-- Popularization Science -->

## Popularization Science

<ul>
{% for member in site.data.repopu %}
  {% if member.category == 'popularization' %}
  <li>
    {{ member.author }} ({{member.year}}) <a href="{{ member.URL }}">  <b>{{ member.name }}</b></a>. <i>{{ member.journal }}</i>{% if member.volume %}, <b>{{ member.volume}}.</b>{% else %}.{% endif %}

    &nbsp;<a href="{{ site.baseurl }}/publications/assets/{{ member.file }}"> <i class="fa fa-file-pdf-o"></i></a>
  </li>
  <br>
  {% endif %}
{% endfor %}
</ul>


<!-- Reports -->

## Reports

<ul>
{% for member in site.data.repopu %}
  {% if member.category == 'report' %}
  <li>
    {{ member.author }} ({{member.year}}) <b>{{ member.name }}</b>. <i>{{ member.journal }}</i>{% if member.volume %}, <b>{{ member.volume}}.</b>{% else %}.{% endif %}

    &nbsp;<a href="{{ site.baseurl }}/publications/assets/{{ member.file }}"> <i class="fa fa-file-pdf-o"></i></a>
  </li>
  <br>
  {% endif %}
{% endfor %}
</ul>
