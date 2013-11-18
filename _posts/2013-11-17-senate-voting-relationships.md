---
layout: post
title: Voting Relationships between Senators
description: "A series of popular network visualizations illustrating how senators in the 101st through 113th Congresses have voted."
modified: 2013-11-17
category: articles
tags: [congress, senate, voting, visualization]
image:
  feature: senate-voting-113-2013.png
comments: false
---

Using voting data from the 101st Congress through the current 113th Congress, I created a series of network visualizations showing voting relationships between senators. They can be found in this [album](http://imgur.com/a/Wmoex#0). I used these visualizations to create the GIF below, which illustrates a widening gap between Democratic and Republican senators.

![Senate Voting Patterns]({{ site.url }}/images/senate-voting-patterns.gif)

These network visualizations were featured on the [Yahoo!](http://news.yahoo.com/the-splitting-of-the-senate--now-in-convenient-gif-form-213908185.html) front page.

<figure>
    <a href="http://i.imgur.com/PFBRsNy.png"><img src="http://i.imgur.com/PFBRsNy.png"></a>
    <figcaption>Yahoo! Front Page Coverage</figcaption>
</figure>

[The Huffington Post](http://www.huffingtonpost.com/2013/11/13/senate-polarization_n_4268863.html?1384374260) and [PolicyMic](http://www.policymic.com/articles/73435/what-s-wrong-with-the-senate-in-one-simple-gif) also ran stories on my visualizations.

I made the graphs using [Gephi](https://gephi.org/), data from [GovTrack](https://www.govtrack.us/data/congress/), and some Python [code](http://nbviewer.ipython.org/urls/gist.github.com/rlucioni/1ef3c5c9412569b4c82d/raw/22bbb04b1ac700fd79c57379ad93c2fe6fc254d5/senate-voting-relationships). In each graph, edge (*u*, *v*) is assigned weight equal to the number of times Senator *u* and Senator *v* voted the same way, either Yea or Nay. For the sake of clarity, I filtered out edges with weight less than 100; these lighter edges generally indicate agreement on procedural votes.

The clusters you see in each graph are the result of using Gephi's Force Atlas layout which applies a physics model to the graph and causes those nodes connected by heavier edges to be pulled together more tightly. A nice side-effect of using this physics model is that more bipartisan senators are pushed closer to the center of the graph, near the party divide, while less bipartisan senators are repelled outwards toward the the perimeter of the graph, furthest from the party divide.
