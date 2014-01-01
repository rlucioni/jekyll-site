---
layout: clean
title: The Evolution of the American Presidency
description: "A study in how the use of presidential power has changed since the inception of the office."
modified: 2013-12-11
category: articles
tags: [american presidency, data sciences]
comments: false
---

<div align="center">
    <img src="http://i.imgur.com/HNZE5pQ.png"></a>
    <br><br>
    <b>Kathy Lin, Renzo Lucioni, Matthew Moellman and Sherrie Wang</b>
    <br><br>
    <a markdown="0" href="https://github.com/rlucioni/executive-evolution" class="btn">View on GitHub</a>
</div>

This screencast accompanies the following article.

<!-- embed screencast here -->
<iframe class="youtube-player" type="text/html" width="640" height="385" src="http://www.youtube.com/embed/Z_ucSP5Fmdk" allowfullscreen frameborder="0">
</iframe>

## Table of Contents ##
* [Overview](#overview)
* [Defining Success](#defining-success)
* [Administrative Power](#administrative)
    * [Executive Orders](#executive-orders)
    * [Vetoes](#vetoes)
    * [Budget and Staff](#budget-staff)
* [Legislative Power](#legislative)
* [Rhetorical Power](#rhetorical)
    * [Predictive Text Analysis](#predictive-text)
* [Conclusions](#conclusions)

<hr>

### <a name="overview"></a> Overview ###

The presidency today is not what it was when George Washington took office. It has changed continuously over time, and several facets of the office have only emerged in modern times. As such, time is a key factor to take into consideration when attempting to compare the many presidents of the United States. However, despite changing times, there are presidents from all periods of American history who are commonly considered "great" presidents. In this project, we study the evolution of the executive office over time and attempt to quantitatively explain the success of "great" presidents such as Washington, Lincoln, and Franklin D. Roosevelt - presidents who faced unique challenges and lived in starkly different times.

More specifically, our goal in this project is to study the evolution of the three main components of presidential power: rhetorical power, administrative power, and legislative power. Using a variety of data collected by UCSB's [American Presidency Project](http://www.presidency.ucsb.edu/), we examine how presidential rhetoric has evolved throughout the history of the executive office, how the president's use of executive power has changed throughout the years, and how the president's interactions with Congress have transformed. In doing so, we gain a quantitative understanding of what makes an administration successful, and develop a method for objectively grouping the presidents.

We see that both executive and legislative power have expanded throughout the years, and that while presidents are exercising their rhetorical power more often, they say less to the public during each address. We also learn that the assertive use of executive power tends to be correlated with successful presidents. Surprisingly, the opposite is true of legislative power.

### <a name="defining-success"></a> Defining Success ###

> The office of the president is so staggeringly complicated that nobody can, by conventional measurement, be "a good president."
>
> \- William F. Buckley, founder of *National Review*

We begin by defining a metric for measuring the success of a president. We combine historical Gallup Presidential Approval Ratings with a collection of academic rankings to create a robust, aggregated ranking of the presidents. Note that approval ratings are only available from the time of FDR's presidency onwards. In addition, keep in mind that approval ratings reflect public sentiment only at the time polls are administered; they do not necessarily align with the way a president is viewed in retrospect. For example, Truman was disliked in his time, but is viewed today as one of the great presidents.

<figure>
    <!-- approval ratings over time -->
    <a href="http://i.imgur.com/m7u4VBD.png"><img src="http://i.imgur.com/m7u4VBD.png"></a>
</figure>

Three distinct groups emerge when we cluster the presidents based on their aggregated rankings. Denoted by red lines, the middle cluster contains those regarded as the "greatest" presidents, including Lincoln, FDR, Washington, and Roosevelt. Denoted by cyan lines, the upper cluster contains those regarded as "good" presidents, including JFK, Polk, and Eisenhower. Denoted by green lines, the lower cluster contains those regarded as "mediocre" presidents, including Nixon, Grant, Carter, and Obama.

<figure>
    <!-- HAC -->
    <a href="http://i.imgur.com/ao50cwi.png"><img src="http://i.imgur.com/ao50cwi.png"></a>
    <figcaption>Red: "greatest" presidents. Teal: "good" presidents. Green: "mediocre" presidents.</figcaption>
</figure>

Grouping the presidents into these three categories prompts us to ask why few presidents are great, many are only good, and some suffer mediocrity. In answering this question, we focus on what the academic world considers to be the three main components of presidential power. The first of these is administrative power, which encompasses the president's use of executive orders, vetoes, appointments, and signing statements. The second is rhetorical power, which encompasses the president's ability to communicate with the public and influence the behavior of others through speech. The third is legislative power, which encompasses the president's relationship with Congress when it comes to passing legislation. 

With these three pillars of the presidency in mind, we direct our attention to the [Siena College Survey](http://www.siena.edu/pages/179.asp?item=2566), which scores each of the presidents on a variety of attributes. We correlate these scores with the overall rankings produced above to determine which attributes are most predictive of presidential success.

<figure>
    <!-- Siena correlations -->
    <a href="http://i.imgur.com/SbP05xk.png"><img src="http://i.imgur.com/SbP05xk.png"></a>
</figure>

Attributes relating to administrative power are colored in red, while those relating to rhetorical power are colored in green and those relating to legislative power are colored in blue; purple denotes attributes unrelated to these three kinds of presidential power. This graph tells us that several attributes most strongly correlated with presidential rankings relate to administrative power; these attributes are "Executive Ability," "Executive Appointments," and "Court Appointments." "Communication" is the only attribute in the survey related to rhetorical power, and it is slightly less correlated with presidential rankings than the administrative attributes. "Relations with Congress" and "Party Leadership" are both attributes related to legislative power, and they are some of the attributes least correlated with presidential rankings.

We use the varying strengths of these correlations to inform our analysis of the three types of presidential power, focusing our efforts on administrative power but also examining aspects of rhetorical and legislative power.


### <a name="administrative"></a> Administrative Power ###

> Suffice it to say that the President is made the sole repository of the executive powers of the United States, and the powers entrusted to him as well as the duties imposed upon him are awesome indeed.
>
> \- William Rehnquist, 16th Chief Justice of the United States

We begin our look into the American presidency by examining the evolution of administrative power. As the head of the executive branch, the president is given power to make appointments, issue executive orders, propose the federal budget, and veto bills from Congress. We expect a president's use of administrative power to reflect the amount of power he possesses, which we suspect is relevant to his popularity and success.

#### <a name="executive-orders"></a> Executive Orders ####

Executive orders have full force of law and are issued by presidents to accomplish tasks ranging from waging war and responding to emergencies to influencing the internal affairs of government. There were no guidelines outlining what executive orders could accomplish until 1952, when the Supreme Court ruled that Executive Order 10340 from President Truman was invalid because it attempted to create a law without Congress rather than simply clarify or extend one. Since then, presidents have cited existing laws to avoid issuing unconstitutional orders.

We visualize the number of executive orders issued by presidents over time and find a general increase from Washington's day to today, with a huge increase in orders issued under President Theodore Roosevelt. Particularly large numbers were issued between Teddy Roosevelt and Harry Truman's presidencies.

<figure>
    <!-- executive orders by president, chronological -->
    <a href="http://i.imgur.com/sVQhD4Z.png"><img src="http://i.imgur.com/sVQhD4Z.png"></a>
</figure>

The top issuers of executive orders include those we know to be the strongest presidents -- that is, presidents who believe they can act in ways not specifically allowed by the Constitution. In particular, wartime presidents Woodrow Wilson and Franklin D. Roosevelt issue the most orders by far, and strong presidents Theodore Roosevelt and Harry Truman are also in the top six.

On the other hand, Presidents Calvin Coolidge, Herbert Hoover, and Warren Harding, who believed that their actions were strictly limited by the Constitution, also issued relatively large numbers of orders. We suspect they are more conservative with the scope of the orders they issued.

<figure>
    <!-- executive orders by president, descending -->
    <a href="http://i.imgur.com/uCW2byI.png"><img src="http://i.imgur.com/uCW2byI.png"></a>
</figure>

From what we can see, there seems to be no clear correlation between a president's party and how many executive orders he issues. This is complicated by the fact that the Democratic and Republican platforms have changed significantly since the inception of both parties.

Next, we investigate the content of executive orders by looking at the single words or pairs of words most used in orders.

<figure>
    <!-- executive orders, most common words -->
    <a href="http://i.imgur.com/tJQSat7.png"><img src="http://i.imgur.com/tJQSat7.png"></a>
</figure>

Unsurprisingly, "shall" is the top word, while words generally referring to the government ("united states", "president", "federal", etc.) round out the top 20.

Below, we highlight the most common words used in executive orders in a few distinct eras. President Theodore Roosevelt, for example, seems to have issued quite a few orders regarding land, as words like "north", "corner township", and "reservation" appear in his top words.

<figure>
    <!-- executive orders, Teddy -->
    <a href="http://i.imgur.com/gzDdXPg.png"><img src="http://i.imgur.com/gzDdXPg.png"></a>
</figure>

In our times, the words "information" and "security" become popular words since George W. Bush's presidency.

<figure>
    <!-- executive orders, post-Bush -->
    <a href="http://i.imgur.com/kfwxSwA.png"><img src="http://i.imgur.com/kfwxSwA.png"></a>
</figure>

The content of executive orders is clearly time-dependent. Thus, while we can quantify how many were issued under each president, such analysis alone would not capture the evolving context of executive orders.

What about the lengths of executive orders over time? The following scatterplot makes it obvious that orders have increased in length, with recent outliers (not shown) reaching as high as 300,000 words. This could indicate the increasing complexity and/or expanding scope of executive orders.

<figure>
    <!-- executive orders, length -->
    <a href="http://i.imgur.com/8XMhbIz.png"><img src="http://i.imgur.com/8XMhbIz.png"></a>
    <figcaption>Executive orders have increased in length.</figcaption>
</figure>

From our exploration so far, we know which presidents used the most executive orders and note the changing nature of these orders.


#### <a name="vetoes"></a> Vetoes ####

Next, we examine the number of vetoes issued over time. Issuance of a veto is the president exercising his power to strike down legislation. An abundance of vetoes can be indicative of discord between the president and Congress, as well as how the president perceives his role as leader of the executive branch. Our data is organized by Congressional number.

<figure>
    <!-- vetoes, chronological -->
    <a href="http://i.imgur.com/gpikkm0.png"><img src="http://i.imgur.com/gpikkm0.png"></a>
</figure>

We see a generally increasing trend in vetoes issued per Congress, with huge spikes under Grover Cleveland and Franklin Roosevelt. A look into history reveals that President Cleveland vetoed a plethora of pension bills and used his presidential powers to limit the size of the federal government. President Roosevelt vetoed the most bills out of any president, partly because there were numerous new solutions proposed for the Great Depression and partly because he served as president for four terms. President Cleveland issued the most vetoes on a per-term and per-Congress basis.

<figure>
    <!-- vetoes, descending, truncated -->
    <a href="http://i.imgur.com/afubaBy.png"><img src="http://i.imgur.com/afubaBy.png"></a>
    <figcaption>Note: The above figure is truncated.</figcaption>
</figure>

This can perhaps be interpreted as another sign of the increasing power of the president (or, alternatively, increasing discord between Congress and the president).

#### <a name="budget-staff"></a> Budget and Staff ####

Since it is the job of the president and the Office of Management and Budget (OMB) to propose the federal budget, we now take a look at the federal receipts and outlays over time as a percent of GDP. The data we obtained starts in 1930.

<figure>
    <!-- receipts and outlays -->
    <a href="http://i.imgur.com/MfJbPJa.png"><img src="http://i.imgur.com/MfJbPJa.png"></a>
</figure>

As usual, Franklin Roosevelt's presidency is uniquely a time of huge outlays and huge deficit. The receipts and outlays as a function of GDP grow from 1930 to the 1950s, and remain relatively constant since then. Another spike in outlays and dip in surplus/deficit can be seen with the recent Great Recession.

<figure>
    <!-- surplus/deficit -->
    <a href="http://i.imgur.com/HLeDH96.png"><img src="http://i.imgur.com/HLeDH96.png"></a>
</figure>

The size of the executive office staff also generally grows over time, with an enormous spike under FDR. It grows from the 1950s to 1970s, then decreases and remains fairly constant.

<figure>
    <!-- staff size -->
    <a href="http://i.imgur.com/yjtlAJh.png"><img src="http://i.imgur.com/yjtlAJh.png"></a>
</figure>

To reveal trends in the data after FDR, we plot the same data on a log scale.

<figure>
    <!-- staff size, log scale -->
    <a href="http://i.imgur.com/frUpk7Z.png"><img src="http://i.imgur.com/frUpk7Z.png"></a>
</figure>

The combined exploration of administrative power shows general growth in power exercised by the president over time. Franklin Roosevelt's presidency is exceptional under all examined metrics. Theodore Roosevelt and Woodrow Wilson's presidencies stand out given their use of executive orders. President Cleveland is unique in his use of vetoes, and, more recently, President Obama also has the formidable task of dealing with the Great Recession.

Furthermore, we performed a multi-variate regression on the number of executive orders, federal surplus/deficit, and GDP growth with presidential approval ratings, and found no significant correlation. Thus, even though administrative power is publicly viewed as the most significant aspect of the presidency, the numbers that we examine above cannot be used as predictors of presidential success.


### <a name="legislative"></a> Legislative Power ###

> An elective despotism was not the government we fought for; but one in which the powers of government should be so divided and balanced among the several bodies of magistracy as that no one could transcend their legal limits without being effectually checked and restrained by the others.
>
> \- James Madison, Federalist No. 58

Although the president himself does not have the power to make a law, he is able to advance his legislative agenda by speaking and writing to members of Congress who *do* have the power to legislate. Historically, presidents have used several means to promote legislation, including The State of the Union address and public papers written to Congress. Our hypothesis is that successful presidents use their legislative power effectively.

The term 'first hundred days' is often used to describe the period of time at the beginning of a president's first term in which the president is expected to reveal his plans for new legislation. The number of requests for legislation made in the first year of a president's term decreases significantly in the Reagan era.

<figure>
    <!-- first year requests for legislation -->
    <a href="http://i.imgur.com/oTXFbdn.png"><img src="http://i.imgur.com/oTXFbdn.png"></a>
</figure>

Presidents use their legislative power in the State of the Union address in different ways: some make many requests for legislation, some make only a few.

<figure>
    <!-- SOTU requests -->
    <a href="http://i.imgur.com/bUiRc68.png"><img src="http://i.imgur.com/bUiRc68.png"></a>
    <figcaption>Most of the requests for legislation in State of the Union addresses are new, but some are repeated.</figcaption>
</figure>

In the graph below, note how the number of State of the Union legislation requests (green) closely matches approval ratings (purple) in the late 1940s, early 1950s.

<figure>
    <!-- normalized count and approval ratings -->
    <a href="http://i.imgur.com/Pzxh2my.png"><img src="http://i.imgur.com/Pzxh2my.png"></a>
</figure>

In addition to requesting legislation in speeches, presidents also write papers to members of the House and the Senate detailing their legislative plans. The evolution of the length of these papers can be seen in the following scatterplot. While the majority of papers written to Congress remains relatively short over the history of the United States, longer papers become more common over the past century.

<figure>
    <!-- lengths of papers over time -->
    <a href="http://i.imgur.com/greHTEw.png"><img src="http://i.imgur.com/greHTEw.png"></a>
    <figcaption>The gap around 1921 is due to missing data. Six papers longer than 150,000 words are not displayed.</figcaption>
</figure>

The following chart shows how many papers each president wrote. The presidents at the top wrote the most papers, and they come from the Democratic and Republican parties that have been dominant for some time. The presidents towards the bottom wrote the fewest papers, and they come from other political parties that are no longer popular.

<figure>
    <!-- counts of papers to congress -->
    <a href="http://i.imgur.com/jlwuyll.png"><img src="http://i.imgur.com/jlwuyll.png"></a>
    <figcaption>Modern presidents seem to write more papers.</figcaption>
</figure>

It turns out that of our hypothesized measures of a president's legislative power, only the number of papers written to Congress was a statistically significant indicator of success.

<figure>
    <!-- approval rating v. log number -->
    <a href="http://i.imgur.com/UP4CWox.png"><img src="http://i.imgur.com/UP4CWox.png"></a>
</figure>

Even though it only explains about 10% of the variation in presidential approval ratings, this model shows us that, on average, the more papers a president writes to Congress in a year, the lower that president's approval rating for that year. This is unlikely to be a direct causal relationship. The reason for this phenomenon could be that the president writes frequently to Congress when the nation has numerous problems to address, which also affects presidential approval ratings at that time. As such, this model should be taken with a grain of salt; it is not to be considered the underlying truth. This model gives us the beginning of a quantitative understanding of what it means for a president to be effective with his legislative power.

### <a name="rhetorical"></a> Rhetorical Power ###

> "Going public"... is a strategy whereby a president promotes himself and his policies in Washington by appealing directly to the American public for support.
>
> \- Samuel Kernell, author of *Going Public*

Rhetorical power involves the use of rhetoric by the president to inspire others to behave differently than they otherwise would. The president applies his rhetorical power to members of Congress, to domestic and foreign governments, and most commonly, to the American public.

Modern presidents address the public more often than their predecessors, but they say less during each address. For example, consider how State of the Union addresses have changed in length over time.

<figure>
    <!-- length of SOTUs over time -->
    <a href="http://i.imgur.com/bfKFaEi.png"><img src="http://i.imgur.com/bfKFaEi.png"></a>
</figure>

After peaking in length in the late 19th century, State of the Union addresses appear to be becoming shorter. Below, we visualize the lengths of the president's Saturday radio addresses.

<figure>
    <!-- length of saturday radio addresses over time -->
    <a href="http://i.imgur.com/mvDoykZ.png"><img src="http://i.imgur.com/mvDoykZ.png"></a>
</figure>

Like State of the Union addresses, the president's Saturday radio addresses appear to be becoming shorter, although much more gradually so.

Despite their reduced length, public addresses dramatically influence the public's perception of the president. This effect is made clear by visualizing approval ratings before and after State of the Union addresses. Below is such a visualization for Bill Clinton.

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

The words and phrases used in presidential addresses can tell us about the themes presidents tend to focus on. First, we examine common words and phrases in State of the Union addresses.

<figure>
    <!-- most common words in SOTUs -->
    <a href="http://i.imgur.com/aUPe29J.png"><img src="http://i.imgur.com/aUPe29J.png"></a>
</figure>

We can visualize these results by using a word cloud.

<figure>
    <!-- SOTU cloud -->
    <a href="http://i.imgur.com/FBnnBOm.png"><img src="http://i.imgur.com/FBnnBOm.png"></a>
</figure>

Unsurprisingly, "government," "congress," and "united states" are some of the most common words and phrases in State of the Union addresses. Others in this list include "people," "great," "war," and "world." Inaugural addresses feature many of these same words.

<figure>
    <!-- most common words in radio addresses -->
    <a href="http://i.imgur.com/ys2Xgdr.png"><img src="http://i.imgur.com/ys2Xgdr.png"></a>
</figure>

As before, we can visualize these results by using a word cloud.

<figure>
    <!-- radio cloud -->
    <a href="http://i.imgur.com/ERuf4xc.png"><img src="http://i.imgur.com/ERuf4xc.png"></a>
</figure>

"People," "america," and "american" top this list, reflecting the target audience of these addresses.

#### <a name="predictive-text"></a> Predictive Text Analysis ####

The [Naive Bayes classifier](http://en.wikipedia.org/wiki/Naive_Bayes_classifier) is a statistical tool commonly used to perform spam email filtering. By applying this tool to presidential Saturday radio addresses, we are able determine which words and phrases best predict a president's party and popularity. 

Words and phrases which are most strongly associated with Democratic presidents include "middle class," "college," "crime," "communities," and "care." Words which are most strongly associated with Republican presidents include "freedom," "god," "terror," "inflation," and "defense."

Words and phrases which are most strongly associated with popular presidents include "parents," "schools," "children," and "challenge." Words and phrases which are most strongly associated with unpopular presidents include "middle class," "troops," "terrorists," "financial," and "market."

Note how popular presidents tend to discuss social progress, while unpopular presidents tend to address domestic and foreign concerns. The words and phrases presidents favor reflect the changing state of the nation. Popular presidents are able to discuss social progress because their time affords them this opportunity. Unpopular presidents often find themselves discussing domestic and foreign problems because they are forced to by the state of the world at the time in which they are in office. As such, we see that the perceived success of a president is determined largely by the challenges of his time.

### <a name="conclusions"></a> Conclusions ###

At the onset of this project, we set out to (1) quantitatively document changes in the American presidency seen throughout its history, and (2) uncover some "objective" predictors of presidential success. We accomplish the former, but do not find strong, consistent predictors of success in numbers. Nevertheless, the qualitative observations we uncover still provide useful insights into the ingredients that may be necessary for presidential greatness.

First, we see that while use of presidential administrative power waxes and wanes, it has generally expanded over time. Landmark presidents such as FDR, Woodrow Wilson, and Teddy Roosevelt are in large part responsible for this expansion, taking the power of the office into their own hands to effect the changes they sought. While abundant use of executive orders and vetoes cannot predict presidential success, we see that the greatest presidents are more likely to have used executive power liberally.

In contrast, we observe that presidents who exercise their legislative power more frequently to interact with Congress tend to be perceived as less successful. We see that presidents today write to Congress more often than their predecessors. More recent papers also tend to be longer. 

Finally, we see that the use of rhetorical power has evolved. Presidents address the public more often than they did a century ago, but they say less each time. We are unable to find a good rhetorical indicator of presidential success, but we find that the words presidents use tend reflect their perceived success. Popular presidents tend to discuss social progress, using words like "parents," "schools," and "children." On the other hand, unpopular presidents often discuss social concerns and foreign policy issues, using words like "middle class," "troops," and "terrorists."

Our conclusions serve as a reminder that the ultimate success of a president is as much a function of the era he inherits as his use of administrative, legislative, and rhetorical power. Some presidents are tested with trying times and rise to the challenge; others are unable to overcome their hurdles, and still others never get the opportunity to prove themselves. Becoming a great president, then, requires a perfect mix of historical context and presidential character.
