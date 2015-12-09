---
layout: post
title:  R and Graphics
author: Kevin Cazelles, Nicolas Casajus
date: 2015-12-04
categories: Rgraphics
---

*'Evolving post' written in collaboration with [Nicolas Casajus](http://nicolascasajus.fr) and [Marie-Hélène Greffard](http://www.er.uqam.ca/nobel/r3424621/labo/fr/site/Marie-Helene.html).*
<br/>
*Last edit: Dec 3, 2015*

<br/>

### Why use R to produce graphics?

S, R's ancestor[^note1], was first designed to be an interactive interface for calling routines from the SCS (Statistical Computing Subroutines) FORTRAN library. It expanded to be a complete programming language dedicated to data manipulation, statistical analysis and data visualization (see [A brief History of S](http://www.lcg.unam.mx/~lcollado/R/resources/history_of_S.pdf)). Today's graphical system of R is directly derived from the one of S. When R is installed[^note2] we get from it two base packages, ['graphics'](https://stat.ethz.ch/R-manual/R-devel/library/graphics/html/00Index.html) and ['grid'](https://stat.ethz.ch/R-manual/R-devel/library/grid/html/00Index.html), which produce graphics that are exported with the [grDevices](https://stat.ethz.ch/R-manual/R-devel/library/grDevices/html/00Index.html) package. These packages are very complete and flexible. They allow users to efficiently create graphics that scientists use in their day to day operations, *i.e.* scatterplots, box plots, histograms, etc. We consider that the 'graphics' package is somewhat more user-friendly than the trickier 'grid' package which offers better facilities to develop new graphical functions (e.g. grid' has been employed to build [ggplot2](https://cran.r-project.org/web/packages/ggplot2)). Recently, the [gridGraphics](https://journal.r-project.org/archive/2015-1/murrell.pdf) package has been developed to bridge the gap between 'grid' and 'graphics' packages.

That being said, the advantages are numerous and more can be built in. For instance:

{% for post in site.posts %}{% if post.title == 'R and me' %}{% assign cool = post.url %}{% endif %}{% endfor %}

1- You obtain all the advantages linked with using R, *i.e.* it is free, lot of documentation exists, a very large community of users, there are many packages, it is easy to learn ([see this former post]({{ cool | prepend: site.baseurl }})).

2- Any kind of graphics a scientist needs has already been implemented by many contributors (see the packages review below). If you find there is room for improvement or that we are mistaken, all information is available to further develop missing plotting functions or correct existing ones.

3- Almost everything is possible. All graphics are fully customizable. Some time is required to learn the works, but it's worth it.

4- Although there may be many good reasons to use software to post-treat graphics R produces in WYSIWYG softwares, we contend that once you master R, you will never do so. When a graphics is done, it is associated with only a few lines of code. Changing solely the lines of code is a much more efficient way more efficient to solve any problem than reproducing and post-treating the graphics. As scientists, it is a victory to only modify a few lines of code when reviewers quibble about a figure.

5- Once a graphics is created, we can export it in many formats: 'eps', 'jpeg', 'pdf', 'bmp', 'svg' with appropriate resolution and size. There is 100% guarantee that you will meet a journal's requirements for figures publication.

This blog is dedicated to help you realize these advantages. Examples will be provided with many parameters to ensure you can get exactly what you want (in term of graphics). We wish to show and assist you in making everything possible. Every tool is already available and we made some more accessible through this [graphicsutils](https://github.com/KevCaz/graphicsutils) package available on github.


<br/>

### Documentation

We will make the content below 'evolving' by collecting and indexing as many sources of documentation as possible. Please comment in the Disqus section below to suggest and/or provide your own sources:


- **Comprehensive R Archive Network** ([CRAN](https://cran.r-project.org))
    - [Manuals](https://cran.r-project.org/manuals.html)
    - [Contributed manuals and cheat sheets](https://cran.r-project.org/other-docs.html)

- **Journals**
  - [R journal](https://journal.r-project.org)
  - [Journal of Statistical Software](http://www.jstatsoft.org/index)

- **Books**:
  - [Rgraphics](http://www.e-reading.club/bookreader.php/137370/C486x_APPb.pdf)    
  - [Rgraphics, Second Edition](http://www.amazon.com/Graphics-Second-Edition-Chapman-Series/dp/1439831769)
  - [ggplot2](http://ms.mcmaster.ca/~bolker/misc/ggplot2-book.pdf)
  - [R Graphics Cookbook](http://www.cookbook-r.com/Graphs/)

- **Blogs**:
  - [inside-R](http://www.inside-r.org)
  - [Quick-R](http://www.statmethods.net/about/learningcurve.html)
  - [Revolutions](http://blog.revolutionanalytics.com/about.html)
  - [R graph gallery](http://rgraphgallery.blogspot.ca)
  - [staRt](http://koenbro.blogspot.ca/?expref=next-blog)


<!-- #### Blog/Personnal Pages

- [Paul Murrel](https://www.stat.auckland.ac.nz/~paul/)
- [Hadley Wickham](http://had.co.nz)


#### Github

- [Hadley Wickham](https://github.com/hadley)
- [Paul Murrel](https://github.com/pmur002)
- [David Lawrence Miller](https://github.com/dill)
- [Gábor Csárdi](https://github.com/gaborcsardi)
- [Karthik Ram](https://github.com/karthik) -->


<br/>

### Packages

Many packages for graphics are indexed in a dedicated [task view maintained by Nicholas Lewin-Koh](https://cran.r-project.org/web/views/Graphics.html). We have indexed many and refer to more in tables below.

- **Main Packages**

| Package name | Short description |
|:-------------|:------------------|
| [graphics](https://stat.ethz.ch/R-manual/R-devel/library/graphics/html/00Index.html) | Base (and S-like) graphics  |
| [grid](https://stat.ethz.ch/R-manual/R-devel/library/grid/html/00Index.html) | A flexible package that supplements 'graphics' |
| [grDevices](https://stat.ethz.ch/R-manual/R-devel/library/grDevices/html/00Index.html) | Graphics Devices and Support for Colours and Fonts |
| [lattice](https://cran.r-project.org/web/packages/lattice) | R implementation of Trellis Graphics |
| [ggplot2](https://cran.r-project.org/web/packages/ggplot2) | R implementation of Leland Wilkinson's "Grammar of Graphics"|
| [plotrix](https://cran.r-project.org/web/packages/plotrix) | Various plotting function
| [gridGraphics](https://cran.r-project.org/web/packages/gridGraphics/) | Functions to convert a page of plots drawn with the graphics package into an identical output drawn with the grid package (see also [this article](https://journal.r-project.org/archive/2015-1/murrell.pdf)))

<br/>

- **Colors**

|[colorscience](https://cran.r-project.org/web/packages/colorscience/index.html) | Methods and data for color science - color conversions by observer, illuminant and gamma |
| [colorspace](https://stat.ethz.ch/R-manual/R-devel/library/grid/html/00Index.html) | A flexible package that supplements 'graphics' |
| [dichromat](https://cran.r-project.org/web/packages/dichromat/index.html) | Collapse red-green or green-blue distinctions to simulate the effects of different types of color-blindness |
| [RColorBrewer](https://cran.r-project.org/web/packages/RColorBrewer/index.html) | Provides color schemes for maps (and other graphics) designed by Cynthia Brewer |
| [wesanderson](https://cran.r-project.org/web/packages/wesanderson/) | Palettes generated mostly from Wes Anderson movies |



<br/>

- **Fonts**

| [extrafont](https://cran.r-project.org/web/packages/extrafont/index.html) | Tools to using fonts other than the standard PostScript fonts |
| [showtext](https://cran.r-project.org/web/packages/showtext/index.html) | Using Fonts More Easily in R Graphs |

<br/>

- **Import and Export images/shapefiles in different format**

| [bmp](https://cran.r-project.org/web/packages/bmp/index.html) | Reads Windows BMP format images |
| [grDevices](https://stat.ethz.ch/R-manual/R-devel/library/grDevices/html/00Index.html) | Graphics Devices and Support for Colours and Fonts |
| [jpeg](https://cran.r-project.org/web/packages/jpeg/index.html) | Reads JPEG bitmap images stored in the JPEG format |
| [pixmap](https://cran.r-project.org/web/packages/pixmap/index.html) | Functions for import, export, plotting and other manipulations of bitmapped images |
| [png](https://cran.r-project.org/web/packages/png/index.html) | Reads bitmap images stored in the PNG format |
| [maptools](https://cran.r-project.org/web/packages/png/index.html) | Set of tools for manipulating and reading geographic data, in particular ESRI shapefiles |
| [raster](https://cran.r-project.org/web/packages/raster/index.html)| Reading, writing, manipulating, analyzing and modeling of gridded spatial data |
| [rgdal](https://cran.r-project.org/web/packages/rgdal/index.html)| Reads shapefiles and raset using Frank Warmerdam's Geospatial Data Abstraction Library |

<br/>

- **Plot 3d**

| [ggplot2](https://cran.r-project.org/web/packages/lattice) | see this [post](http://www.r-bloggers.com/3d-plots-with-ggplot2-and-plotly/) as an example |
| [lattice](https://cran.r-project.org/web/packages/lattice) | see functions `cloud()` and `wireframe()` |
| [misc3d](https://cran.r-project.org/web/packages/misc3d/index.html) | Reads bitmap images stored in the PNG format |
| [plot3D](https://cran.r-project.org/web/packages/plot3D/index.html) | Plotting multi-dimensional data |
| [scatterplot3d](https://cran.r-project.org/web/packages/scatterplot3d/index.html) | Reads JPEG bitmap images stored in the JPEG format |

<br/>

- **Maps**

| [cartography](https://cran.r-project.org/web/packages/cartography/index.html) | Create and integrate maps in your R workflow |
| [leaflet](https://cran.r-project.org/web/packages/leaflet/index.html) | Create Interactive Web Maps with the JavaScript 'Leaflet' library |
| [OpenStreetMap](https://cran.r-project.org/web/packages/OpenStreetMap/index.html) | Accesses high resolution raster maps using the OpenStreetMap protocol|
| [maps](https://cran.r-project.org/web/packages/maps/index.html) | Draw Geographical Maps |



<br/>

- **Other plotting functions/packages**

| [ape](https://cran.r-project.org/web/packages/ape/index.html) | Analyses of Phylogenetics and Evolution, see `plot.phylo()` and `plot.multiPhylo()` |
| [igraph](https://cran.r-project.org/web/packages/igraph/index.html) |  Graph visualization, see `plot.igraph()`  |
| [shape](https://cran.r-project.org/web/packages/shape/index.html) | Functions for plotting graphical shapes, colors |
| [vcd](https://cran.r-project.org/web/packages/vcd/index.html) | Visualizing Categorical Data |



<br/>


[^note1]: R has strongly inherited from S and Scheme, see [Genesis](https://cran.r-project.org/doc/html/interface98-paper/paper_1.html).

[^note2]: The last version is 3.2.2, [29 base and recommended packages](https://stat.ethz.ch/R-manual/R-devel/library) are installed by default.

<br/>

#### That's all Folks

<br/>
