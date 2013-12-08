---
layout: clean
title: The Evolution of the American Presidency
description: "A study in how the use of presidential power has changed since the inception of the office."
modified: 2013-12-11
category: articles
tags: [cs109, data science, american presidency]
comments: false
published: false
---

<div align="center">
    <img src="http://i.imgur.com/HNZE5pQ.png"></a>
    <br><br>
    <b>By Renzo Lucioni, Kathy Lin, Sherrie Wang, and Matthew Moellman</b>
    <br><br>
    <a markdown="0" href="https://github.com/rlucioni/cs109-project" class="btn">View on GitHub</a>
</div>

Our goal in this project was to study the evolution of the three main components of presidential power: rhetorical power, administrative power, and legislative power. We learned how presidential rhetoric has evolved throughout the history of the executive office, how the president's use of executive power has changed throughout the years, and how the president's interactions with Congress have transformed. In doing so, we gained a more objective understanding of what makes an administration successful, as measured by Gallup approval ratings, and developed a method for objectively grouping the presidents.

This screencast accompanies the following article.

<!-- embed screencast here -->
<iframe class="youtube-player" type="text/html" width="640" height="385" src="http://www.youtube.com/embed/2bqEn8AXzJ4" allowfullscreen frameborder="0">
</iframe>

## Table of Contents ##
* [The Rhetorical Presidency](#rhetorical)
* [The Administrative Presidency](#administrative)
* [The Legislative Presidency](#legislative)
* [Grouping the Presidents](#grouping)

### <a name="rhetorical"></a> The Rhetorical Presidency ###

We can also visualize how, for a particular president, approval ratings change before and after a State of the Union address. Here's such a visualization for Bill Clinton.

<div align="center">
    <!-- Clinton SOTUs and approval ratings -->
    <img src="http://i.imgur.com/FDUjUiD.png"></a>
</div>

Here's another such visualization, this one for George W. Bush.

<div align="center">
    <!-- George W. Bush SOTUs and approval ratings -->
    <img src="http://i.imgur.com/LyhYyr5.png"></a>
</div>

In both examples shown here, we see that a president's approval rating tends to drop immediately after a State of the Union address. 

We can also visualize how State of the Union addresses have changed in length over time.

<div align="center">
    <!-- length of SOTUs over time -->
    <img src="http://i.imgur.com/bfKFaEi.png"></a>
</div>

After peaking in length in the late 19th century, State of the Union addresses appear to be becoming shorter. We can perform the same exercise for the president's Saturday radio addresses.

<div align="center">
    <!-- length of saturday radio addresses over time -->
    <img src="http://i.imgur.com/mvDoykZ.png"></a>
</div>

Like State of the Union addresses, the president's Saturday radio addresses appear to be becoming shorter, although much more gradually so.

We can determine which words and phrases presidents favor in their speeches. Let's first examine common words in State of the Union addresses.

<div align="center">
    <!-- most common words in SOTUs -->
    <img src="http://i.imgur.com/aUPe29J.png"></a>
</div>

Unsurprisingly, "government," "congress," and "united states" are some of the most common words and phrases. Others in this list include "people," "great," "war," and "world." Inaugural addresses feature many of these same words.

<div align="center">
    <!-- most common words in inaugurals -->
    <img src="http://i.imgur.com/sfvfwa1.png"></a>
</div>

Again, "government" and "people" top the list, followed closely by "states," "great," and "world."

### <a name="administrative"></a> The Administrative Presidency ###

### <a name="legislative"></a> The Legislative Presidency ###

### <a name="grouping"></a> Grouping the Presidents ###

We can use the insights gathered above regarding the rhetorical, administrative, and legislative presidencies to objectively group the presidents. One way of achieving this is through the use of a network visualization. In the visualization below, each node represents a president. An edge between president **u** and president **v** represents the inverse of the difference between the two presidents' average approval ratings. A physics-based model has been applied to the graph, pulling nodes connected by heavier edges closer together. As a result, presidents with similar approval ratings appear closer together in the graph.

<div align="center">
    <!-- ratings network -->
    <img src="http://i.imgur.com/H0GGU0E.png"></a>
</div>

Despite this graph's sparseness, it still communicates some interesting details. The strong connections between Ford and Carter, and between LBJ and Clinton, immediately stand out. This suggests that these pairs of presidents were similarly successful. Obama's proximity to Carter may suggest that their presidencies have so far been perceived to be similarly unsuccessful. The nodes representing FDR and JFK are far removed from the other nodes, mirroring the perception of their presidencies as remarkably successful.

The groupings observed in this network visualization are confirmed by hierarchical agglomerative clustering.