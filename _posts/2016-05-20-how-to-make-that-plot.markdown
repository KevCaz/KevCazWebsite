---
layout: post
title:  How to make that plot?
author: Kevin Cazelles, Nicolas Casajus, Steve Vissault, Zofia Taranu
date: 2017-05-28
categories: Rgraphics
---
<!-- ## Y'a un problem  -->

*'Evolving post' written in collaboration with [Nicolas Casajus](http://nicolascasajus.fr), [Steve Vissault](http://steveviss.github.io) and [Zofia Taranu](http://zofiaecaterinataranu.weebly.com)*
<br/>
*Last edit: May 12, 2016*


http://www.statmethods.net/graphs/pie.html

http://www.statmethods.net/graphs


<br/>

This blog post complements the previous one.
While the latter gathers packages, this one is graphic-oriented meaning
that it provide

We provide way in base graphics ggplot and indicates package if required.
It intends to gather a list of chart and to provide a way to do it using R.


- <a href=""><i class="fa fa-area-chart"></i></a> :  do it with a base function of base packages
- <a href=""><i class="fa fa-bar-chart"></i></a> : do it with a funciton of **ggplot2**
- <a href=""><i class="fa fa-line-chart"></i></a> : use another package
- <a href=""><i class="fa fa-globe"></i></a> : refers to an additional source of information (such as a blog post)



{% assign plt_by_cat = site.data.Rplts | group_by:"category" | sort:"name" %}


{% for plt_cat in plt_by_cat %}
  <br/>
  <h3 id="{{plt_cat.name}}"> {{plt_cat.name}} </h3>
  <ul>
    {% for plt in plt_cat.items %}
      <li>
        <a href="https://cran.r-project.org/web/packages/{{plt.nameplt}}/index.html">{{plt.nameplt}}</a>:   <i>{{plt.text}}</i>
        {% if plt.basecode %} {{plt.basecode}}
        {% if plt.base %} <a href="{{plt.blogbase}}"><i class="fa fa-area-chart"></i></a> {% endif %}
        {% if plt.ggplot %} <a href="{{plt.ggplot}}"><i class="fa fa-bar-chart"></i></a> {% endif %}
        {% if plt.blogpost %} <a href="{{plt.blogpost}}"><i class="fa fa-globe"></i></a> {% endif %}
        {% if plt.doi %} <a href="https://doi.org/{{plt.doi}}"><i class="fa fa-link"></i></a> {% endif %}
        {% if plt.pdf %}  <a href="{{plt.pdf}}"><i class="fa fa-file-pdf-o"></i></a> {% endif %}

      </li>
    {% endfor %}
  </ul>
{% endfor %}



<br/>
