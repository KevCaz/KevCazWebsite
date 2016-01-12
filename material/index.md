---
layout: default
title: Material
order: 3
---

## R packages

- Some R functions to ease the edition of graphics using the base package *graphics*: [graphicsutils](https://github.com/KevCaz/graphicsutils) [![Travis](https://travis-ci.org/KevCaz/graphicsutils.svg?branch=master)](https://travis-ci.org/KevCaz/graphicsutils)

       devtools::install_github("KevCaz/graphicsutils")

- A small package to convert numbers from one base to another [decomposenumber](https://github.com/KevCaz/decomposenumbers):

      devtools::install_github("KevCaz/decomposenumbers"))

<br/>

## Manuals

<ul>
{% for member in site.data.manual %}
  <li>
    {{ member.author }} ({{member.year}}) <b> {{ member.name }}</b>
    {%if member.file %}
    &nbsp;<a href="{{ site.baseurl }}/material/assets/{{ member.file }}"> <i class="fa fa-file-pdf-o"></i></a>
    {% endif %}
    {%if member.github %}
    &nbsp;<a href="{{ member.github }}"><i class="fa fa-github"></i></a>
    {% endif %}
  </li>
  <br/>
{% endfor %}
</ul>

<br/>

## Presentation (teaching)

<ul>
{% for member in site.data.teachpres %}
  <li>
    {{ member.author }} ({{member.year}})
    {%if member.URL %}
      {%if member.hosted %}
        <a href="{{ site.baseurl }}/material/assets/{{ member.URL }}">{{ member.name }} ({{ member.lang }})</a>
      {% else %}
        <a href="{{ member.URL }}">{{ member.name }} ({{ member.lang }})</a>
      {% endif %}
    {% else %}
      <b> {{ member.name }} </b>
    {% endif %}
    {%if member.download %}
      <a href="{{ site.baseurl }}/material/assets/{{ member.download }}"><i class="fa fa-download"></i></a>
    {% endif %}
  </li>
  <br/>
{% endfor %}
</ul>
