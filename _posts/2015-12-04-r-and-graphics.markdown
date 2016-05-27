---
layout: post
title:  R and Graphics
author: Kevin Cazelles, Nicolas Casajus
date: 2015-12-04
categories: Rgraphics
---

*'Evolving post' written in collaboration with [Nicolas Casajus](http://ahasverus.github.io), [Steve Vissault](http://steveviss.github.io) and [Marie-Hélène Greffard](http://www.er.uqam.ca/nobel/r3424621/labo/fr/site/Marie-Helene.html).*
<br/>
*Last edit: May 14, 2016*

<br/>

## Why use R to produce graphics?

S, R's ancestor[^note1], was first designed to be an interactive interface for calling routines from the SCS (Statistical Computing Subroutines) FORTRAN library. It expanded to be a complete programming language dedicated to data manipulation, statistical analysis and data visualization (see [A brief History of S](http://www.lcg.unam.mx/~lcollado/R/resources/history_of_S.pdf)). Today's graphical system of R is directly derived from the one of S. When R is installed[^note2] we get from it two base packages, ['graphics'](https://stat.ethz.ch/R-manual/R-devel/library/graphics/html/00Index.html) and ['grid'](https://stat.ethz.ch/R-manual/R-devel/library/grid/html/00Index.html), which produce graphics that are exported with the [grDevices](https://stat.ethz.ch/R-manual/R-devel/library/grDevices/html/00Index.html) package. These packages are very complete and flexible. They allow users to efficiently create graphics that scientists use in their day to day operations, *i.e.* scatterplots, box plots, histograms, etc. We consider that the 'graphics' package is somewhat more user-friendly than the trickier 'grid' package which offers better facilities to develop new graphical functions (e.g. grid' has been employed to build [ggplot2](https://cran.r-project.org/web/packages/ggplot2)). Recently, the [gridGraphics](https://journal.r-project.org/archive/2015-1/murrell.pdf) package has been developed to bridge the gap between 'grid' and 'graphics' packages.

That being said, the advantages are numerous and more can be built in. For instance:

{% for post in site.posts %}{% if post.title == 'R and me' %}{% assign cool = post.url %}{% endif %}{% endfor %}

1. You obtain all the advantages linked with using R, *i.e.* it is free, lot of documentation exists, a very large community of users, there are many packages, it is easy to learn ([see this former post]({{ cool | prepend: site.baseurl }})).

2. Any kind of graphics a scientist needs has already been implemented by many contributors (see the packages review below). If you find there is room for improvement or that we are mistaken, all information is available to further develop missing plotting functions or correct existing ones.

3. Almost everything is possible. All graphics are fully customizable. Some time is required to learn the works, but it's worth it.

4. Although there may be many good reasons to use software to post-treat graphics R produces in WYSIWYG softwares, we contend that once you master R, you will never do so. When a graphics is done, it is associated with only a few lines of code. Changing solely the lines of code is a much more efficient way more efficient to solve any problem than reproducing and post-treating the graphics. As scientists, it is a victory to only modify a few lines of code when reviewers quibble about a figure.

5. Once a graphics is created, we can export it in many formats: 'eps', 'jpeg', 'pdf', 'bmp', 'svg' with appropriate resolution and size. There is 100% guarantee that you will meet a journal's requirements for figures publication.

<!-- This blog section is dedicated to help you realize these advantages. Examples will be provided with many parameters to ensure you can get exactly what you want (in term of graphics). We wish to show and assist you in making everything possible. Every tool is already available and we made some more accessible through this [graphicsutils](https://github.com/KevCaz/graphicsutils) package available on github.
 -->

<br/>


## Documentation

We will make the content below 'evolving' by collecting and indexing as many sources of documentation as possible. Please comment in the Disqus section below to suggest and/or provide your own sources:


- **Comprehensive R Archive Network** ([CRAN](https://cran.r-project.org))
  - [Manuals](https://cran.r-project.org/manuals.html)
  - [Contributed manuals and cheat sheets](https://cran.r-project.org/other-docs.html)

- **Journals**
  - [R journal](https://journal.r-project.org)
  - [Journal of Statistical Software](http://www.jstatsoft.org/index)

- **Books**:
  - [Rgraphics, Second Edition](https://www.stat.auckland.ac.nz/~paul/RG2e/index.html)
  - [ggplot2](http://ms.mcmaster.ca/~bolker/misc/ggplot2-book.pdf)
  - [R Graphics Cookbook](http://www.cookbook-r.com/Graphs/)

- **Blogs**:
  - [R-bloggers](http://www.r-bloggers.com)
  - [inside-R](http://www.inside-r.org)
  - [Quick-R](http://www.statmethods.net/about/learningcurve.html)
  - [Revolutions](http://blog.revolutionanalytics.com/about.html)
  - [R graph gallery](http://rgraphgallery.blogspot.ca)
  - [A newer graph gallery](http://www.r-graph-gallery.com)


<br/>


## Packages



<!-- Find package [here](http://rpackages.ianhowson.com) A comprehensive index of R packages and documentation from CRAN, Bioconductor, GitHub and R-Forge. (https://cran.r-project.org/web/packages/available_packages_by_name.html) -->
Many packages for graphics are indexed in a dedicated [task view maintained by Nicholas Lewin-Koh](https://cran.r-project.org/web/views/Graphics.html). We have indexed many of them and refer to more below. For each package, we provide :

  - the name of the package with a link that goes to the [CRAN](https://cran.r-project.org) repository where the manual and optional vignettes can be found,
  - a text summarizing the package content (an adequate part of the description found online),

when available, we also provide :

  - <a href=""><i class="fa fa-github"></i></a> : a link that goes to the[Github](https://github.com) repository,
  - <a href=""><i class="fa fa-bitbucket"></i></a> : a link that goes to the associated [Bitbucket](https://bitbucket.org) repository,
  - <a href=""><i class="fa fa-globe"></i></a> : a link that goes to a dedicated website or a html vignette that describes well the package,
  - <a href=""><i class="fa fa-link"></i></a> : a link that goes to a relevant publication,
  - <a href=""><i class="fa fa-file-pdf-o"></i></a> : a link that goes to an relevant pdf file (an R journal article for instance).


{% assign pkg_by_cat = site.data.Rpkgs | group_by:"category" | sort:"name" %}

{% for pkg_cat in pkg_by_cat %}
  <br/>
  <h3 id="{{pkg_cat.name}}"> {{pkg_cat.name}} </h3>
  <ul>
    {% for pkg in pkg_cat.items %}
      <li>
        <a href="https://cran.r-project.org/web/packages/{{pkg.namepkg}}/index.html">{{pkg.namepkg}}</a>:   {{pkg.text}}
        {% if pkg.github %} <a href="https://github.com/{{pkg.github}}"><i class="fa fa-github"></i></a> {% endif %}
        {% if pkg.bitbuck %} <a href="https://bitbucket.org/{{pkg.bitbuck}}"><i class="fa fa-bitbucket"></i></a> {% endif %}
        {% if pkg.website %} <a href="{{pkg.website}}"><i class="fa fa-globe"></i></a> {% endif %}
        {% if pkg.doi %} <a href="https://doi.org/{{pkg.doi}}"><i class="fa fa-link"></i></a> {% endif %}
        {% if pkg.pdf %}  <a href="{{pkg.pdf}}"><i class="fa fa-file-pdf-o"></i></a> {% endif %}

      </li>
    {% endfor %}
  </ul>
{% endfor %}


<br/>


-That's all folks-



[^note1]: R has strongly inherited from S and Scheme, see [Genesis](https://cran.r-project.org/doc/html/interface98-paper/paper_1.html).

[^note2]: The last version is 3.2.3, [29 base and recommended packages](https://stat.ethz.ch/R-manual/R-devel/doc/html/packages.html) are installed by default.

<!-- / -->



<br/>
