---
layout: post
title: Voting Relationships between Senators
description: "A series of network visualizations illustrating how senators in the 101st through 113th Congresses have voted."
modified: 2014-06-22
category: articles
tags: [senate, voting, visualization]
comments: false
---

<script>
 (function(d, t) {
    var g = d.createElement(t),
        s = d.getElementsByTagName(t)[0];
    g.src = 'http://assets.gfycat.com/js/gfyajax-0.517d.js';
    s.parentNode.insertBefore(g, s);
}(document, 'script'));
</script>

> "Though America’s political polarisation has become a fact of life, it has never been seen so graphically: as a diseased brain, with few neural pathways between the two hemispheres."
>
> \- *The Economist*, December 7 issue

Using voting data from the 101st Congress through the 113th Congress, I created a series of network visualizations like the one below showing voting relationships between US senators.

<figure>
    <a href="http://i.imgur.com/0iIxJGh.jpg" target="_blank"><img src="http://i.imgur.com/0iIxJGh.jpg"></a>
    <figcaption>113th Congress, 2013 Session. Click image for a larger version.</figcaption>
</figure>

This image and twenty-four others like it can be found in this <a href="http://imgur.com/a/Wmoex#0" target="_blank" title="album">album</a>. I used these visualizations to create the animation below, which illustrates a widening gap between Democratic and Republican senators.

<div align="center">
    <img class="gfyitem" data-id="FloweryDirtyGermanshorthairedpointer" />
</div>

I made the graphs using <a href="https://gephi.org/" target="_blank" title="Gephi">Gephi</a>, roll call data from <a href="https://www.govtrack.us/data/congress/" target="_blank" title="GovTrack">GovTrack</a>, and <a href="http://nbviewer.ipython.org/urls/gist.githubusercontent.com/anonymous/11267960/raw/32ffb765372a3470738914b9c287e14f166ad5ac/svv.ipynb" target="_blank" title="this Python code">this Python code</a>. In each graph, edge (*u*, *v*) is assigned weight equal to the number of times Senator *u* and Senator *v* voted the same way, either Yea or Nay. For the sake of clarity, I filtered out edges with weight less than 100; these lighter edges generally indicate agreement on procedural votes.

The clusters you see in each graph are the result of using Gephi's Force Atlas layout, which applies a force-directed algorithm to the graph and causes those nodes connected by heavier edges to be pulled together more tightly. A nice side-effect of using this physics-based model is that more bipartisan senators are pushed closer to the center of the graph, near the party divide, while less bipartisan senators are repelled outwards toward the perimeter of the graph, furthest from the party divide.

These network visualizations were first featured on the <a href="http://news.yahoo.com/the-splitting-of-the-senate--now-in-convenient-gif-form-213908185.html" target="_blank" title="Yahoo!">Yahoo!</a> front page.

<figure>
    <a href="http://news.yahoo.com/the-splitting-of-the-senate--now-in-convenient-gif-form-213908185.html" target="_blank"><img src="http://i.imgur.com/PFBRsNy.png"></a>
    <figcaption>Yahoo! Front Page Coverage</figcaption>
</figure>

*The Economist* then picked up the story, running <a href="http://www.economist.com/news/united-states/21591190-united-states-amoeba?frsc=dg%7Ca" target="_blank" title="this short piece">this short piece</a> in the print edition of the newspaper dated December 7, 2013. *The Economist* also produced the following narrated animation.

<iframe class="youtube-player" type="text/html" width="640" height="385" src="http://www.youtube.com/embed/ieDieiho17s" allowfullscreen frameborder="0">
</iframe>

<!-- [*The Huffington Post*](http://www.huffingtonpost.com/2013/11/13/senate-polarization_n_4268863.html?1384374260), [*The Washington Post*](http://www.washingtonpost.com/blogs/the-fix/wp/2013/12/06/american-politics-as-a-diseased-brain/), and [*PolicyMic*](http://www.policymic.com/articles/73435/what-s-wrong-with-the-senate-in-one-simple-gif) also ran stories on my visualizations. 

On December 10, 2013, my visualizations were featured on [*Hardball with Chris Matthews*](http://www.nbcnews.com/id/3036697/vp/47452493#53795037), accompanied by an article on [MSNBC.com](http://www.msnbc.com/hardball/visualization-washington-dysfunction). The relevant clip appears below.

<iframe class="youtube-player" type="text/html" width="640" height="385" src="http://www.youtube.com/embed/RttuF3jnD78" allowfullscreen frameborder="0">
</iframe> -->
