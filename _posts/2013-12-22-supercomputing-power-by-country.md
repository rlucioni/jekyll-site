---
layout: post
title: Supercomputing Power by Country
description: "Visualizing the amount of supercomputing power held by countries on the TOP500 list."
modified: 2013-12-22
category: articles
tags: [supercomputing, power, visualization]
comments: false
---

I created the following visualizations to illustrate the amount of supercomputing power held by countries on the TOP500 list. The data on supercomputing power was taken from the TOP500 [November 2013 ranking](http://www.top500.org/list/2013/11/) of supercomputers according to the LINPACK benchmark. The data on country populations, used to calculate the per capita totals, was taken from Wikipedia's [List of countries by population](http://en.wikipedia.org/wiki/List_of_countries_by_population).

<figure>
    <!-- tflops per country -->
    <a href="http://i.imgur.com/8rAWqV9.png"><img src="http://i.imgur.com/8rAWqV9.png"></a>
</figure>

<figure>
    <!-- mflops per capita, by country -->
    <a href="http://i.imgur.com/uWoInOY.png"><img src="http://i.imgur.com/uWoInOY.png"></a>
</figure>

The code I wrote to create these visualizations can be found [here](http://nbviewer.ipython.org/gist/rlucioni/b92e848ae1da41ffa452).