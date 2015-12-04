---
layout: post
title:  "Latex and Ecology Letters"
author: Kevin Cazelles
date: 2015-01-26
categories: Latex
---


I have been working with [Latex](http://www.latex-project.org) since 2011 and I love it. I did so, first and foremost, to benefit from its mathematical writing facility. After a couple of months, I realized the potentiality of Latex and I have been trying to improve my Latex skills ever since. Now I even strive to avoid the use of other preparing document softwares (I like [LibreOffice](http://www.libreoffice.org), though). However I recognize that it could be difficult to share your work when your collaborators are no Latex users (copy and paste to LibreOffice.... yuk!). Latex is very helpful to submit paper except when the journal does not have adequate Latex template or even worst, when the journal explicitly demand to avoid submitting Latex files.

I have recently submitted an article to [Ecology Letters](http://onlinelibrary.wiley.com/journal/10.1111/(ISSN)1461-0248) (rejected, sadly!). Unfortunately, the journal do not provide any Latex files as explained in the author guidelines. Their layout expectations are readily met except for the reference style. This means we need to look for an appropriate .bst (BibTex STyle) file. The first thing we do in such situation is to address our problem to an Internet search engine. So I did and I got one ".bst" file [here](http://schneider.ncifcrf.gov/latex.html) (a very valuable link by the way). However it wasn't exactly what I expected. Then I ask one of my colleagues who told me he was currently using [Pandoc](http://pandoc.org). I have installed Pandoc and... it was great! Given a "style.csl" file (CSL=Citation Style Language) you can find [here](https://github.com/citation-style-language/styles), together with your latex file "input.tex", your bibliography file "bibli.bib" and a template file (which includes your packages, commands...) you can get an adequate "output.pdf" file using the command following:

    $ pandoc input.tex -o output.file --csl=style.csl  —bibliography=bibli.bib —template templ.tex

or if the submission in pdf format is not allowed you can also produce a new Latex file where all will be written (including) in the main ".tex" file.

    $ pandoc input.tex -o output.tex --csl=style.csl  —bibliography=bibli.bib —template templ.tex

I feel that becoming familiar with Pandoc could help to save a lot of time in the future. However I was not entirely satisfied as the submission requires to number references and to add break line after each number (as explained in the author guidelines). I didn't want to add them manually (note that you can do so in the ".bbl" file produced). Therefore I pushed myself to understand how a ".bst" file works. First of all, I looked for a similar existing ".bst" file and found the "apalike" style (have a look [here](http://ftp.math.utah.edu/pub/tex/bibtex/)). Then, I have tried to introduce slight changes and track the consequences in the output. For some changes it is an appropriate method (*e.g.* to turn "and" into "&" ) but for others (*e.g.* to limit the number of author written) it remains a desperate attempt. Eventually, I had a look on this valuable [document](http://tug.ctan.org/info/bibtex/tamethebeast/ttb_en.pdf) and change the ".bst" file myself the few lines below explain how to use it:


1- Before the beginning of your document ("\\begindocument") add:

    \usepackage{apalike}

2- Insert the file provided [<i class="fa fa-download"></i>]({{site.baseurl}}/blog/assets/my_ecol_let.zip) like so (given that *your_biblio.bib* contains your references):

    \bibliographystyle{my_ecol_let}  
    \bibliography{your_biblio}

<br/>

#### I hope this could help!

<br/>
