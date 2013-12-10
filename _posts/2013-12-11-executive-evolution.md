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

This screencast accompanies the following article.

<!-- embed screencast here -->
<iframe class="youtube-player" type="text/html" width="640" height="385" src="http://www.youtube.com/embed/oHg5SJYRHA0" allowfullscreen frameborder="0">
</iframe>

## Table of Contents ##
* [Overview](#overview)
* [Defining Success](#defining-success)
* [Administrative Power](#administrative)
    * [Executive Orders](#executive-orders)
    * [Vetoes](#vetoes)
    * [Budget and Staff](#budget-staff)
* [Rhetorical Power](#rhetorical)
    * [Characterizing Addresses](#char-addrs)
    * [Predictive Text Analysis](#predictive-text)
* [Legislative Power](#legislative)
* [Conclusions](#conclusions)

<hr>

### <a name="overview"></a> Overview ###

The presidency today is not what it was when George Washington took office. It has changed continuously over time, and several facets of the office have only emerged in modern times. As such, time is a key factor to take into consideration when attempting to compare the many presidents of the United States. However, despite changing times, there are presidents from all periods of American history who are commonly regarded to be "great" presidents. In this project, we studied the evolution of the executive office over time and attempted to objectively explain the success of "great" presidents such as Washington, Lincoln, and Franklin D. Roosevelt - presidents who faced unique challenges and lived in starkly different times.

More specifically, our goal in this project was to study the evolution of the three main components of presidential power: rhetorical power, administrative power, and legislative power. We learned how presidential rhetoric has evolved throughout the history of the executive office, how the president's use of executive power has changed throughout the years, and how the president's interactions with Congress have transformed. In doing so, we gained a more objective understanding of what makes an administration successful, as measured by Gallup approval ratings, and developed a method for objectively grouping the presidents.

### <a name="defining-success"></a> Defining Success ###

We began by defining a metric for measuring the success of a president. We combined historical Gallup Presidential Approval Ratings with a collection of academic rankings to create a robust, aggregated ranking of the presidents. Note that approval ratings are only available from the time of FDR's presidency onwards. In addition, keep in mind that approval ratings reflect public sentiment only at the time polls were administered; they do not necessarily align with the way a president is viewed in retrospect. For example, Truman was disliked in his time, but is viewed today as one of the great presidents.

<figure>
    <!-- approval ratings over time -->
    <a href="http://i.imgur.com/kN74SCO.png"><img src="http://i.imgur.com/kN74SCO.png"></a>
</figure>

Three distinct groups emerge when we cluster the presidents based on their aggregated rankings. Denoted by red lines, the middle cluster contains those regarded as the "greatest" presidents, including Lincoln, FDR, Washington, and Roosevelt. Denoted by cyan lines, the upper cluster contains those regarded as "good" presidents, including JFK, Polk, and Eisenhower. Denoted by green lines, the lower cluster contains those regarded as "mediocre" presidents, including Nixon, Grant, Carter, and Obama.

<figure>
    <!-- HAC -->
    <a href="http://i.imgur.com/4mITpBH.png"><img src="http://i.imgur.com/4mITpBH.png"></a>
</figure>

Grouping the presidents into these three categories prompted us to ask why a few presidents are great, many are only good, and some suffer mediocrity. In answering this question, we focused on what the academic world considers to be the three main components of presidential power. The first of these is administrative power, which encompasses the president's use of executive orders, vetoes, appointments, and signing statements. The second is rhetorical power, which encompasses the president's ability to communicate with the public and influence the behavior of others through speech. The third is legislative power, which encompasses the president's relationship with Congress when it comes to passing legislation. 

With these three pillars of the presidency in mind, we directed our attention to the Siena College Survey which scores each of the presidents on a variety of attributes. We correlated these scores with the overall rankings.

<figure>
    <!-- Siena correlations -->
    <a href="http://i.imgur.com/nRBn0O5.png"><img src="http://i.imgur.com/nRBn0O5.png"></a>
</figure>

Attributes relating to administrative power are colored in red, while those relating to rhetorical power are colored in green and those relating to legislative power are colored in blue; purple denotes attributes unrelated to these three kinds of presidential power. This graph tells us that several of those attributes most strongly correlated with presidential rankings relate to administrative power; these attributes are "Executive Ability," "Executive Appointments," and "Court Appointments." "Communication" is the only attribute in the survey related to rhetorical power, and it is slightly less correlated with presidential rankings than the administrative attributes. "Relations with Congress" and "Party Leadership" are both attributes related to legislative power, and they are some of the attributes least correlated with presidential rankings.

We used the varying strengths of these correlations to inform our analysis of the three types of presidential power, focusing our efforts on administrative power but also examining aspects of rhetorical and legislative power.


### <a name="administrative"></a> Administrative Power ###

#### <a name="executive-orders"></a> Executive Orders ####

<figure>
    <!-- executive orders by president, chronological -->
    <a href="http://i.imgur.com/EpWoWEm.png"><img src="http://i.imgur.com/EpWoWEm.png"></a>
</figure>

<figure>
    <!-- executive orders by president, descending -->
    <a href="http://i.imgur.com/BIyPuZ7.png"><img src="http://i.imgur.com/BIyPuZ7.png"></a>
</figure>

<figure>
    <!-- executive orders, most common words -->
    <a href="http://i.imgur.com/tJQSat7.png"><img src="http://i.imgur.com/tJQSat7.png"></a>
</figure>

<figure>
    <!-- executive orders, Teddy -->
    <a href="http://i.imgur.com/gzDdXPg.png"><img src="http://i.imgur.com/gzDdXPg.png"></a>
</figure>

<figure>
    <!-- executive orders, post-Bush -->
    <a href="http://i.imgur.com/kfwxSwA.png"><img src="http://i.imgur.com/kfwxSwA.png"></a>
</figure>

<figure>
    <!-- executive orders, length -->
    <a href="http://i.imgur.com/8XMhbIz.png"><img src="http://i.imgur.com/8XMhbIz.png"></a>
</figure>


#### <a name="vetoes"></a> Vetoes ####

<figure>
    <!-- vetoes, chronological -->
    <a href="http://i.imgur.com/gpikkm0.png"><img src="http://i.imgur.com/gpikkm0.png"></a>
</figure>

<figure>
    <!-- vetoes, descending, truncated -->
    <a href="http://i.imgur.com/afubaBy.png"><img src="http://i.imgur.com/afubaBy.png"></a>
</figure>

#### <a name="budget-staff"></a> Budget and Staff ####

<figure>
    <!-- receipts and outlays -->
    <a href="http://i.imgur.com/i7eqg4z.png"><img src="http://i.imgur.com/i7eqg4z.png"></a>
</figure>

<figure>
    <!-- surplus/deficit -->
    <a href="http://i.imgur.com/HLeDH96.png"><img src="http://i.imgur.com/HLeDH96.png"></a>
</figure>

<figure>
    <!-- staff size -->
    <a href="http://i.imgur.com/yjtlAJh.png"><img src="http://i.imgur.com/yjtlAJh.png"></a>
</figure>


### <a name="rhetorical"></a> Rhetorical Power ###

#### <a name="char-addrs"></a> Characterizing Addresses ####

We can visualize how, for a particular president, approval ratings change before and after a State of the Union address. Here's such a visualization for Bill Clinton.

<figure>
    <!-- Clinton SOTUs and approval ratings -->
    <a href="http://i.imgur.com/FDUjUiD.png"><img src="http://i.imgur.com/FDUjUiD.png"></a>
</figure>

Here's another such visualization, this one for George W. Bush.

<figure>
    <!-- George W. Bush SOTUs and approval ratings -->
    <a href="http://i.imgur.com/LyhYyr5.png"><img src="http://i.imgur.com/LyhYyr5.png"></a>
</figure>

In both examples shown here, we see that a president's approval rating tends to drop immediately after a State of the Union address. 

We can also visualize how State of the Union addresses have changed in length over time.

<figure>
    <!-- length of SOTUs over time -->
    <a href="http://i.imgur.com/bfKFaEi.png"><img src="http://i.imgur.com/bfKFaEi.png"></a>
</figure>

After peaking in length in the late 19th century, State of the Union addresses appear to be becoming shorter. We can perform the same exercise for the president's Saturday radio addresses.

<figure>
    <!-- length of saturday radio addresses over time -->
    <a href="http://i.imgur.com/mvDoykZ.png"><img src="http://i.imgur.com/mvDoykZ.png"></a>
</figure>

Like State of the Union addresses, the president's Saturday radio addresses appear to be becoming shorter, although much more gradually so.

We can determine which words and phrases presidents favor in their speeches. Let's first examine common words in State of the Union addresses.

<figure>
    <!-- most common words in SOTUs -->
    <a href="http://i.imgur.com/aUPe29J.png"><img src="http://i.imgur.com/aUPe29J.png"></a>
</figure>

Unsurprisingly, "government," "congress," and "united states" are some of the most common words and phrases. Others in this list include "people," "great," "war," and "world." Inaugural addresses feature many of these same words.

<figure>
    <!-- SOTU cloud -->
    <a href="http://i.imgur.com/FBnnBOm.png"><img src="http://i.imgur.com/FBnnBOm.png"></a>
</figure>

<figure>
    <!-- most common words in radio addresses -->
    <a href="http://i.imgur.com/ys2Xgdr.png"><img src="http://i.imgur.com/ys2Xgdr.png"></a>
</figure>

"People" and "america" top this list, reflecting the target audience of these addresses.

<figure>
    <!-- radio cloud -->
    <a href="http://i.imgur.com/ERuf4xc.png"><img src="http://i.imgur.com/ERuf4xc.png"></a>
</figure>

#### <a name="predictive-text"></a> Predictive Text Analysis ####

Words that best predict a popular president in a Saturday radio address include "parents," "schools," "children," and "challenge." Words that best predict an unpopular president in a Saturday radio address include "middle class," "troops," "terrorists," and "iraq."


### <a name="legislative"></a> Legislative Power ###


### <a name="conclusions"></a> Conclusions ###

We can use the insights gathered above regarding the rhetorical, administrative, and legislative presidencies to objectively group the presidents. One way of achieving this is through the use of a technique known as hierarchical agglomerative clustering.