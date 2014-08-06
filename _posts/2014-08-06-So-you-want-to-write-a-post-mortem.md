---
author: hector
date: 2014-08-01
title: 'So, you want to write a post-mortem? Our internal guide for post-mortems'
category: 2penny
layout: post
image: 
  feature: DevOpsDaysLogo.png
published: true
tags: ops post-mortem reliability process
comments: true
share: true
---

So you want to write a post-mortem...
=====================================

Time ago I wrote this guide to help my colleagues (ops or devs) to write a 
good postmortem. I think it is worth it to share with everybody. 

Writing a good post-mortem is almost art. Here we will explain some basic guidelines to get it done.

You must understand and believe why you write it
------------------------------------------------

Why should we write a post-mortem? 

Is just because there is an over-worried ops guy bitching you to get it done?  Or is there any actual value there? 

The post-mortem tries to achieve these goals:

-   **Recover (or even improve) the trust of the stakeholders . **Transparency works! ( [http://www.transparentuptime.com/2010/07/why-transparency-works.html](http://www.transparentuptime.com/2010/07/why-transparency-works.html))
    We are *committed*to deliver a *stable, high-available and quality platform,* and when there is a problem, or a feature is not working as expected, we are failing to our stakeholders, and they know that.
    But even worse, if we don't admit failure and show that we are under control and learning and fixing, everybody will stop trusting us, even our own team.
-   **Learn and improve** It is OK to fail, but is not OK not learn from that. Every failure is a great opportunity to learn and improve our products and workflow.
-   **Don't repeat mistakes**, you don't want to repeat one time and other the same mistakes and problems. Keeping everything documented will help here.
-   **Keep everybody updated** when there is a outage, usually only affected users and who fixed it are aware of it. But is important that all the team, and the business, understands and visualizes the real status and health of our projects.

Know your readers
-----------------

You must write your post-mortem knowing who is going to read it:

-   **End users and Customer Services:** They want to know which features were affected, how the company is working to prevent this problem, how to workaround the issue, how to identify it if  it happens again.
-   **Business stakeholders, BAs, PO:** They want to know what was the business impact, which part of the project caused the problem, why it happened, what we should prioritize to fix it,
-   **Developers:** They need to know how to reproduce the problem, what are the login messages, technically what happened.
-   **QA:** The need to know how they can identify future problems like this, technically what happened, etc.
-   **24x7 support:** They need to know how identify and diagnose the problem, which monitoring is needed, additional documentation/runbooks needed.
-   **Infrastructure/Support teams (network, sysops, platform engineering):** They need to know if they were related in the outage, how they can help to improve/avoid the situation.
-   **Other teams:** They want to learn from our experiences.

What the post-mortem should cover
---------------------------------

In this blog post, they cover the requisites and expectations of a good post-mortem: [http://www.transparentuptime.com/2010/03/guideline-for-postmortem-communication.html](http://www.transparentuptime.com/2010/03/guideline-for-postmortem-communication.html)

I will copy it here.

### Prerequisites:

1.  **Admit failure** - *Hiding downtime is no longer an option*
2.  **Sound like a human** - *Do not use a standard template, do not apologize for "inconveniencing" us*
3.  **Have a communication channel** - *Set up a process to handle incidents prior the event (e.g. [public health dashboard](http://www.transparentuptime.com/2008/11/rules-for-successful-public-health.html), status blog, twitter account, etc.)*
4.  **Above all else, be authentic** *- You must be believed to be heard*

### Requirements:

1.  **Start time and end time of the incident**
2.  **Who/what was impacted** - *Should I be worried about this incident?*
3.  **What went wrong** -*What broke and how you fixed it (with insight into the root cause analysis process)*
4.  **Lessons learned** - *What's being done to improve the situation for the future, in technology, process, and communication*

### **Bonus:**

1.  Details on the technologies involved
2.  Answers to the [Five Why's](http://en.wikipedia.org/wiki/5_Whys)
3.  Human elements - heroic efforts, unfortunate coincidences, effective teamwork, etc
4.  What others can learn from this experience

References
==========

There are plenty of references about writing post-mortems. Here are some and **feel free to add more**

Some readings...
----------------

-   Why transparency works? [http://www.transparentuptime.com/2010/07/why-transparency-works.html](http://www.transparentuptime.com/2010/07/why-transparency-works.html)
-   Benefits of transparency: [http://www.transparentuptime.com/2010/07/benefits-of-transparency.html](http://www.transparentuptime.com/2010/07/benefits-of-transparency.html)
-   Free Book "The human side of Postmortems"  [http://oreilly.com/radarreports/the-human-side-of-postmortems.csp](http://oreilly.com/radarreports/the-human-side-of-postmortems.csp)
-   Blog dedicated to "Transparent uptime" [http://www.transparentuptime.com/](http://www.transparentuptime.com/)
-   Guideline for a nice postmortem: [http://www.transparentuptime.com/2010/03/guideline-for-postmortem-communication.html](http://www.transparentuptime.com/2010/03/guideline-for-postmortem-communication.html)
-   Analysis of a google postmortem: [http://www.transparentuptime.com/2010/03/google-app-engine-downtime-postmortem.html](http://www.transparentuptime.com/2010/03/google-app-engine-downtime-postmortem.html)

Some videos
-----------

-   Talk from Lenny Rachitsky (Webmetrics/Neustar), "The Upside of Downtime: How to Turn a Disaster Into an Opportunity": https://www.youtube.com/watch?v=6MF2Pu6IW3Q
-   Velocity 2012: Richard Cook, "How Complex Systems Fail": https://www.youtube.com/watch?v=2S0k12uZR14

Some nice post-mortems and status pages
---------------------------------------

-   Heroku postmortem when Amazon went down [https://status.heroku.com/incidents/151](https://status.heroku.com/incidents/151)
-   Heroku's status page: [https://status.heroku.com/](https://status.heroku.com/)
-   Github status page: [https://status.github.com/](https://status.github.com/)
-   Amazon's postmortem on outage on Apr 21st [http://aws.amazon.com/message/65648/](http://aws.amazon.com/message/65648/)
-   Google App Engine postmortem: [https://groups.google.com/forum/\#!topic/google-appengine/p2QKJ0OSLc8](https://groups.google.com/forum/#%21topic/google-appengine/p2QKJ0OSLc8)

