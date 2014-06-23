---
layout: post
title: Objective Product Management
description: "A summary of my edX internship during the summer of 2013."
modified: 2014-06-23
category: articles
tags: [edX, internship, engineering, product]
comments: false
---

I had a great time as an intern at <a href="https://www.edx.org/" target="_blank" title="edX">edX</a> in the summer of 2013. During my time there, I worked to enable an objective approach to product management. My summer project consisted of several discrete improvements ranging across edX's Learning Management System and the newly-formed Analytics team. My project was as much about getting the "process" right as it was about remedying the LMS' way of showing students their progress. By "process" I mean: identifying and validating changes, implementing them, and then quantifying their impact. Enabling and promoting this "process" was the umbrella covering the work I did during the summer.

<figure>
    <a href="http://i.imgur.com/j0WUzke.jpg" target="_blank"><img src="http://i.imgur.com/j0WUzke.jpg"></a>
</figure>

Here's an outline of the process we try to follow here at edX. We start by concretely identifying an issue and the effect we expect to see by resolving it. We identify issues to address by using analytics data we gather. We then brainstorm potential solutions. The next step is validation. Before fully implementing changes, we want to validate them. Changes can be motivated by any number of things, but we want to make sure that any proposed changes fix the issue at hand. There are many ways to validate a set of changes. They could be shown internally to a handful of people, run by a group of users we bring in to test them, or made the subject of a split test, also known as an A/B test. If we see that the changes help, we implement them. If they don't make a significant difference, it's back to step one. After making the changes, we want to measure their real impact in production to make sure we're getting the return we expected from the validation step.

## Analytics and Data Quality

To help with the identification and quantification steps, my work focused on analytics and data quality. <a href="https://segment.io/" target="_blank" title="Segment.io">Segment.io</a> is a third-party service which allows us to send our analytics data to any analytics service we want without having to integrate with each service individually. I integrated Segment.io with the edX platform and cleaned up the events we log. We now use Segment.io to track what users are doing as they interact with the courseware, forwarding this information to <a href="http://www.google.com/analytics/" target="_blank" title="Google Analytics">Google Analytics</a>, and <a href="https://mixpanel.com" target="_blank" title="Mixpanel">Mixpanel</a>.

## Building an A/B Testing Framework

To improve the validation step of our process, I developed a flexible and 
lightweight approach to split testing. Also referred to as A/B testing, split testing consists of dividing users into groups, controlling what these groups see (we want to show something different to each group), and monitoring and comparing the behavior of each. We wanted our split testing approach to be flexible, allowing us to apply it across the edX platform to changes ranging from cosmetic alterations to entirely new features. The split testing framework I implemented relies on <a href="http://waffle.readthedocs.org/en/latest/index.html" target="_blank" title="Waffle">Waffle</a>, a Django feature flipper. I decided not to use one of the several open-source A/B testing frameworks available for Django because the majority are not compatible with Django 1.4, are no longer maintained, or are either poorly documented or entirely undocumented. I also felt that these frameworks were too rigid for our desired use cases, perhaps as a result of over-abstracting the process of split testing. Most frameworks that I found were designed with the express purpose of tracking user signups or purchases. I thought that using Waffle in conjunction with Mixpanel would constitute a more flexible and lightweight approach.

Waffle provides three tools for controlling what users see: flags, switches, and samples. My framework uses Waffle's session-based flags to toggle features in Django views and Mako templates. Flags fit the split-testing bill well. They can be assigned to all users, a group of users, or an arbitrary percentage of users. Given appropriate permissions to the "Flags" model in the database, flags can be created, toggled, and deleted using the Django admin site without involving DevOps. In addition, changes made to flags go into effect immediately without the need to push any code. My framework keeps track of which flags are active for a particular user by adding a property to Segment.io API calls which contains a string listing active flags; this particular change was made in <a href="https://github.com/edx/edx-platform/blob/master/lms/templates/widgets/segment-io.html?source=cc" target="_blank" title="segment-io.html">segment-io.html</a>. Segment.io routes this information to Mixpanel where we can study the data, allowing us to compare the behavior of different groups of users.

## In-context Progress Display

Here's an example of the process in action. While speaking with groups of edX users, we learned that there was a strong desire for an in-context display of progress. Students were having a hard time visualizing their progress in a course. They also had minimal help in navigating the courseware. At present, the courseware landing page tells a student where he or she was last and links to that component. However, the course accordion does not indicate what the student has completed, what the student is currently working on, or what the student has not yet started. To make matters worse, the progress tab is completely divorced from the courseware and is also too verbose, meaning the page is not immediately useful to a student. Students had no way of reliably measuring their progress from within the context of the courseware.

I attempted to address this issue by displaying students' scores live, right next to the titles of the problems they were working on. Here's what a typical question used to look like:

<figure>
    <img src="http://i.imgur.com/bTdegxe.png">
    <figcaption>Before In-context Scores</figcaption>
</figure>

Here's what the same question looked like after my changes:

<figure>
    <img src="http://i.imgur.com/MzGGkNo.png">
</figure>
<figure>
    <img src="http://i.imgur.com/MIewo29.png">
    <figcaption>After In-context Scores</figcaption>
</figure>

To make these changes, I modified <a href="https://github.com/edx/edx-platform/blob/master/common/lib/xmodule/xmodule/capa_module.py?source=cc" target="_blank" title="capa_module.py">capa_module.py</a> and <a href="https://github.com/edx/edx-platform/blob/master/common/lib/xmodule/xmodule/js/src/capa/display.coffee?source=cc" target="_blank" title="display.coffee">display.coffee</a>. We try to reserve split testing for big, risky changes, not clear wins like this change; we want to validate at the right level. As such, validation of this change consisted of showing the change internally. Implementation of this feature was followed by quantification: we observed an 8% drop in traffic from the courseware to the progress page.

EdX has only just started using analytics data to inform decisions made internally, but I'm confident that doing so will allow the organization to make better choices. Part of edX's mission is to discover what helps people learn online, and I think that a more quantitative approach can help the organization reach that goal.
