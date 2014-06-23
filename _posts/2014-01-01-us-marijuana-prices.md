---
layout: post
title: Marijuana Prices in the United States
description: "Visualizing the US price per gram of marijuana by quality and year."
modified: 2014-06-22
category: articles
tags: [marijuana, price, visualization]
comments: false
---

In November, landmark votes significantly eased marijuana laws in Colorado and Washington State. Today, Colorado becomes the first state in the nation to permit the sale and use of marijuana for recreational purposes. Washington State expects to begin legal marijuana sales this spring. 

In light of these recent developments, I was curious about how the price of marijuana has changed nationally over the last few years. Using transaction data collected anonymously by <a href="http://www.priceofweed.com/" target="_blank" title="priceofweed.com">priceofweed.com</a> and made available by Zachary M. Jones on <a href="https://github.com/zmjones/priceofweed" target="_blank" title="GitHub">GitHub</a>, I assembled the following series of twelve choropleth maps. Note that the prices shown here most likely correspond to bulk purchases.

<figure>
    <a href="http://i.imgur.com/ewZJhQW.png" target="_blank"><img src="http://i.imgur.com/ewZJhQW.png"></a>
    <figcaption>Click image for a larger version.</figcaption>
</figure>

Prices for high quality marijuana appear to be consistently lowest closer to the West Coast, and have dropped considerably since 2010. As of 2013, one gram of high quality marijuana can be most cheaply purchased in Washington State, Oregon, or Colorado. A single gram of high quality marijuana appears to be most expensive in North Dakota.

In 2010, medium quality marijuana appears to have been cheapest in the South. Since then, prices have become more uniform. As of 2013, one gram of medium quality marijuana can be most cheaply purchased in Washington State, Oregon, California, or Colorado, but also in Mississippi, Alabama, or South Carolina.

The price of a single gram of low quality marijuana appears to be consistently lowest in the South and Southwest. More recently, cheap, low quality marijuana can also be found in Washington State, California, Montana, Wisconsin, Ohio, Vermont, or Delaware.

My code, raw images (SVG and PNG), and all associated data can be found on <a href="https://github.com/rlucioni/viz/tree/master/marijuana" target="_blank" title="GitHub">GitHub</a>. A brief technical note: I manually colored these maps, using Python to determine which hex color codes to use for each state. In retrospect, D3 would have been a much better tool for this job, and I would have used it had I been more familar with it at the time.  

On January 6, 2014, *The Washington Post* featured these choropleth maps in an article on its <a href="http://www.washingtonpost.com/blogs/govbeat/wp/2014/01/06/how-much-does-marijuana-cost-in-the-u-s/" target="_blank" title="GovBeat">GovBeat</a> blog.
