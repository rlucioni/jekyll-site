---
layout: post
title: Engineering an Objective Approach to Product Management
description: "A summary of my work during the summer of 2013 at edX."
modified: 2013-11-16
category: articles
tags: [edX, internship, engineering, product]
image:
  feature: current-edx-logo.png
comments: false
---

These [slides](https://docs.google.com/presentation/d/1RyP2hFUDIWPWpLxAbitOT-Rf3Xf4P9KJXpRLKjcUJe8/edit?usp=sharing) accompany the following summary.

I had a great time this past summer as an intern at edX. I've been working on allowing for and promoting an objective approach to product management. My summer project consisted of several discrete improvements ranging across the LMS and the newly-formed Analytics team. My project was as much about getting the "process" right as it was about remedying the LMS' way of showing students their progress. By "process" I mean: identifying and validating changes, implementing them, and then quantifying their impact. Enabling and promoting this "process" is the umbrella covering the work I did during the summer.

Here's an outline of the process we try to follow here at edX. We start by concretely identifying a problem and the effect we expect to see by fixing it. We identify issues to address by using analytics data we gather. We then brainstorm potential solutions. The next step is validation. Before fully implementing changes, we want to validate them. Changes can be motivated by any number of things, but we want to make sure that the proposed changes fix the problem. There are many ways to validate. It could mean showing the change internally to a handful of people, running it by a group of users we bring in to test the change, or performing split testing. If we see that the change helps, we implement it. If it doesn't, it's back to step one. After making the change, we want to measure its real impact in production to make sure we're getting the return we expected from the validation step.

## Analytics and Data Quality

To help with the identification and quantification steps, my work focused on analytics and data quality. [Segment.io](https://segment.io/) is a third-party service which allows us to send our analytics data to any analytics service we want without having to integrate with each service individually. I integrated Segment.io with the edX platform and cleaned up the events we log. We now use Segment.io to track what users are doing as they interact with the courseware, forwarding this information to [Google Analytics](http://www.google.com/analytics/), [Mixpanel](https://mixpanel.com), and [Chartbeat](https://chartbeat.com/).

## Building an A/B Testing Framework

To improve the validation step of our process, I developed a flexible and 
lightweight approach to split testing. Also referred to as A/B testing, split testing consists of dividing our users into groups, controlling what these groups see (we want to show something different to each group), and monitoring and comparing the behavior of each. We wanted our split testing approach to be flexible, allowing us to apply it across the edX platform to changes ranging from cosmetic alterations to entirely new features. The split testing framework I implemented relies on [Waffle](http://waffle.readthedocs.org/en/latest/index.html), a Django feature flipper. I decided not to use one of the several open-source A/B testing frameworks available for Django because the majority are not compatible with Django 1.4, are no longer maintained, and are either poorly documented or entirely undocumented. What is more, in an attempt to abstract the process of split testing, these frameworks are too rigid for our typical use cases. Most are designed with the express purpose of tracking user signups or purchases. Using Waffle in conjunction with Mixpanel constitutes a more flexible and lightweight approach.

Waffle provides three tools for controlling what users see: flags, switches, and samples. My framework uses Waffle's session-based flags to toggle features in Django views and Mako templates. Flags fit the split-testing bill well. They can be assigned to all users, a group of users, or an arbitrary percentage of users. Given appropriate permissions to the "Flags" model in the database, flags can be created, toggled, and deleted using the Django admin site without involving DevOps. In addition, changes made to flags go into effect immediately without the need to push any code. My framework keeps track of which flags are active for a particular user by adding a property to Segment.io API calls which contains a string listing active flags; this particular change was made in [segment-io.html](https://github.com/edx/edx-platform/blob/master/lms/templates/widgets/segment-io.html?source=c). Segment.io routes this information to Mixpanel where we can study the data, allowing us to compare the behavior of different groups of users.

## In-context Progress Display

Here's an example of the process in action. Speaking with groups of edX users, we learned that there was a strong desire for an in-context display of progress. Students have historically had a hard time visualizing their progress in a course. They have also had minimal help when navigating the courseware. At present, the courseware landing page tells a student where he or she was last and links to that component. However, the course accordion does not indicate what the student has completed, what the student is currently working on, or what the student has not yet started. To make matters worse, the progress tab is divorced from the courseware and is also too verbose, meaning the page is not immediately useful to a student. Students have no way of reliably measuring their progress from within the context of the courseware.

I attempted to address this issue by displaying students' scores live, right next to the titles of the problems they're working on. Here's what a typical question looked like before my changes:

<figure>
    <img src="http://i.imgur.com/bTdegxe.png">
    <figcaption>Before In-context Scores</figcaption>
</figure>

Here's what the same question can look like after my changes:

<figure>
    <img src="http://i.imgur.com/MzGGkNo.png">
</figure>
<figure>
    <img src="http://i.imgur.com/MIewo29.png">
    <figcaption>After In-context Scores</figcaption>
</figure>

To effect these changes, I modified [capa_module.py](https://github.com/edx/edx-platform/blob/master/common/lib/xmodule/xmodule/capa_module.py?source=cc) and [display.coffee](https://github.com/edx/edx-platform/blob/master/common/lib/xmodule/xmodule/js/src/capa/display.coffee?source=cc). We try to reserve split testing for big, risky changes, not clear wins like this change; we want to validate at the right level. As such, validation of this change consisted of showing the change internally. Implementation of this feature is now being followed by quantification. We've observed an 8% drop in traffic from the courseware to the progress page, and we'll use this data to inform future changes.

While we've only just started using analytics data to inform our decisions and this new framework for split testing new work, I'm confident that these tools will allow us to make better choices. One of edX's goals is to discover what helps people learn online. A more quantitative approach will help us reach this goal.
