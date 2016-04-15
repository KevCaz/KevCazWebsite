---
layout: post
title: Empty your plot
author: Kevin Cazelles
date: 2017-02-24
packages:
  - graphics
categories: Rgraphics
---

Why empty your plot ?
---------------------

R offers many graphical facilities, however when using *graphics* default plot are not very nice. We always have to customize to get the figure we really want. In my opinion the main advantage we take from starting from and empty plot is to control every elements we add and by doing so to wander to what extent it is necessary to add it / how he changes the look.

There are many ways to empty plots. I do not want to list all of them, instead I would like to provide three quick ways to do so.

Let us start with a


    val1 <- runif(10)
    val2 <- rnorm(10)
    plot(val1, val2)
