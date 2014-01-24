---
layout: post
title: Supercomputing Power by Country
description: "Visualizing the amount of supercomputing power held by countries on the TOP500 list."
modified: 2014-01-23
category: articles
tags: [supercomputing, power, visualization]
comments: false
---

I created the following visualizations to illustrate the amount of supercomputing power held by countries on the TOP500 list. The data on supercomputing power was taken from the TOP500 [November 2013 ranking](http://www.top500.org/list/2013/11/) of supercomputers according to the LINPACK benchmark. The graph on the right uses a log scale to depict the same data as the graph on the left. I included this log scale graph to help visualize differences between the bars appearing only as thin lines on the left.

<figure>
    <!-- tflops per country -->
    <a href="http://i.imgur.com/yQvzBeT.png"><img src="http://i.imgur.com/yQvzBeT.png"></a>
    <figcaption>Click for a larger version.</figcaption>
</figure>

The United States, China, and Japan top the list, with Germany, France, the United Kingdom and Switzerland trailing them. India's total is surprisingly low.

I was also curious about the amount of supercomputing power available per capita in each of these countries. The data on country populations, used to calculate the per capita totals, was taken from Wikipedia’s [List of countries by population](http://en.wikipedia.org/wiki/List_of_countries_by_population). As before, the graph on the right uses a log scale to depict the same data as the graph on the left.

<figure>
    <!-- mflops per capita, by country -->
    <a href="http://i.imgur.com/zdDxjY7.png"><img src="http://i.imgur.com/zdDxjY7.png"></a>
    <figcaption>Click for a larger version.</figcaption>
</figure>

Switzerland's high per capita totals may be attributable to the country's small population and the number of academic research institutions located there. The United States remains in second place, while China has dropped to 17th place. As expected, India ranks last among these countries in terms of per capita supercomputing power.

The code I wrote to create these visualizations can be found [here](http://nbviewer.ipython.org/gist/rlucioni/b92e848ae1da41ffa452).