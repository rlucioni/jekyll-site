---
layout: post
title: Voting Relationships between Senators
description: "A series of popular network visualizations illustrating how senators in the 101st through 113th Congresses have voted."
modified: 2013-12-15
category: articles
tags: [senate, voting, visualization]
image:
  feature: senate-voting-113-2013.png
comments: false
---

> Though America’s political polarisation has become a fact of life, it has never been seen so graphically: as a diseased brain, with few neural pathways between the two hemispheres.
>
> The Economist, December 7 issue

Using voting data from the 101st Congress through the current 113th Congress, I created a series of network visualizations showing voting relationships between senators. They can be found in this [album](http://imgur.com/a/Wmoex#0). I used these visualizations to create the GIF below, which illustrates a widening gap between Democratic and Republican senators.

![Senate Voting Patterns]({{ site.url }}/images/senate-voting-patterns.gif)

I made the graphs using [Gephi](https://gephi.org/), roll call data from [GovTrack](https://www.govtrack.us/data/congress/), and this [Python code](http://nbtest.herokuapp.com/gist/rlucioni/7796000). In each graph, edge (*u*, *v*) is assigned weight equal to the number of times Senator *u* and Senator *v* voted the same way, either Yea or Nay. For the sake of clarity, I filtered out edges with weight less than 100; these lighter edges generally indicate agreement on procedural votes.

The clusters you see in each graph are the result of using Gephi's Force Atlas layout, which applies a force-directed algorithm to the graph and causes those nodes connected by heavier edges to be pulled together more tightly. A nice side-effect of using this physics-based model is that more bipartisan senators are pushed closer to the center of the graph, near the party divide, while less bipartisan senators are repelled outwards toward the perimeter of the graph, furthest from the party divide.

These network visualizations were first featured on the [Yahoo!](http://news.yahoo.com/the-splitting-of-the-senate--now-in-convenient-gif-form-213908185.html) front page.

<figure>
    <a href="http://news.yahoo.com/the-splitting-of-the-senate--now-in-convenient-gif-form-213908185.html"><img src="http://i.imgur.com/PFBRsNy.png"></a>
    <figcaption>Yahoo! Front Page Coverage</figcaption>
</figure>

[*The Economist*](http://www.economist.com/blogs/graphicdetail/2013/12/daily-chart) then picked up the story, running [this short piece](http://www.economist.com/news/united-states/21591190-united-states-amoeba?frsc=dg%7Ca) in the print edition of the newspaper dated December 7, 2013. In addition, *The Economist* produced the following narrated animation.

<iframe class="youtube-player" type="text/html" width="640" height="385" src="http://www.youtube.com/embed/ieDieiho17s" allowfullscreen frameborder="0">
</iframe>

[*The Huffington Post*](http://www.huffingtonpost.com/2013/11/13/senate-polarization_n_4268863.html?1384374260), [*The Washington Post*](http://www.washingtonpost.com/blogs/the-fix/wp/2013/12/06/american-politics-as-a-diseased-brain/), and [*PolicyMic*](http://www.policymic.com/articles/73435/what-s-wrong-with-the-senate-in-one-simple-gif) also ran stories on my visualizations. 

On December 10, 2013, my visualizations were featured on [*Hardball with Chris Matthews*](http://www.nbcnews.com/id/3036697/vp/47452493#53795037), accompanied by an article on [MSNBC.com](http://www.msnbc.com/hardball/visualization-washington-dysfunction). The relevant clip appears below.

<iframe class="youtube-player" type="text/html" width="640" height="385" src="http://www.youtube.com/embed/RttuF3jnD78" allowfullscreen frameborder="0">
</iframe>
