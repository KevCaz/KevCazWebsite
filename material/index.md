---
layout: default
title: Material
order: 3
---

## R packages

- Some R functions that to help edit graphics: [graphicsutils](https://github.com/KevCaz/graphicsutils) [![Travis](https://img.shields.io/travis/rust-lang/rust.svg)](https://travis-ci.org/KevCaz/graphicsutils/builds/90854166)

       devtools::install_github("KevCaz/graphicsutils")

- A small convert numbers from one base to another [decomposenumber](https://github.com/KevCaz/decomposenumbers)

      devtools::install_github("KevCaz/decomposenumbers"))



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
  <br>
{% endfor %}
</ul>
