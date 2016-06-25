---
layout: default
title: Material
order: 3
---

## R packages
<hr/>

<br/>
<br/>

### [graphicsutils](https://github.com/KevCaz/graphicsutils)

 some R functions to ease the edition of graphics using the base package *graphics*:

 [![Travis](https://travis-ci.org/KevCaz/graphicsutils.svg?branch=master)](https://travis-ci.org/KevCaz/graphicsutils)


<br/>

### [letiRmisc](https://github.com/letiR/letiRmisc)

Some miscellaneous R functions :

  [![Build  status](https://ci.appveyor.com/api/projects/status/x5ngkcflyfiixr37?svg=true)](https://ci.appveyor.com/project/KevCaz/letirmisc)
  [![Travis](https://travis-ci.org/letiR/letiRmisc.svg?branch=master)](https://travis-ci.org/letiR/letiRmisc)
  [![codecov](https://codecov.io/gh/letiR/letiRmisc/branch/master/graph/badge.svg)](https://codecov.io/gh/letiR/letiRmisc)


<br/>

### [decomposenumber](https://github.com/KevCaz/decomposenumbers):

 A small package to convert numbers from one base to another


<br/>

## Manuals
<hr/>

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
<hr/>

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
