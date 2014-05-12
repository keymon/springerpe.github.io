---
author: jefe_problemas 
date: 2014-05-08
title: 'About the way we work'
category: process
layout: post
image: 
  feature: trello-banner.png
published: true
tags: scrum, kanban, srum-ban, scrumban, agile, distributed, team
---

Well...

As a team we are distributed across multiple locations, we are based in London, Dordrecht, Heidelberg and Berlin at the moment. This brings along some challenges, since our development teams don't work in a distributed fashion. We have Development teams present in all of those locations, but each Dev team is sharing the same roof.

Development is done using the Agile methodology and this is one reason for us to also work in an agile and lean way. But as stated, being distributed has some extra challenges. In this post we will describe how we decided to work and find ways to overcome this distributed setup.

###Scrum-Ban
For our more strategic work, we decided to use Scrum and for the more operational Ad-Hoc work we try to follow a Kanban workflow. 
We have iterations (sprints) of two weeks in which we do our strategic (planned) work and keep some headroom for unplanned work.

We start of every iteration with a planning session, done using Google Hangouts. During this session we take work from the backlog, move it to the new iteration. Based on what has most value we decide what we will work on for the next two weeks, leaving headroom for incidents and urgent requests. 

We then start the iteration and use Kanban to get work to done, more on the Kanban board later. Incidents, requests and other unplanned activities that come in, that can’t wait until the next iteration, get thrown into the Kanban board as we go. We strive to record as much work as we can, in order to be able to do better reporting.

Every morning we have a “stand-up” over Google Hangouts, each of us tells what he/she was working on yesterday and what the plan is for today and if there’s any blockers. This is also a good opportunity to ask for help, but it is not the place to resolve issues and have long discussions, these should be held separately.

Once every iteration we have a “Story Time” session, aka Backlog Grooming, in order to keep focus on the valuable stuff. This session is also used to write new stories, reprioritise and to support the upcoming planning session.

At the end of every iteration we have a “Review” session, in which we go over the work that was done and the work that we did not complete. We try to find out why certain tasks got stuck and not completed and how we can improve this for the next iteration.

To conclude the whole iteration we have a showcase to our stakeholders to inform and show what we have completed and what is upcoming. This is also a place where the stakeholders can ask questions, the showcase is done over webconference.


###The Boards
To structure our work and make it visible we use [Trello](http://www.trello.com). We have created two main Trello boards, one for the backlog and one for the current Iteration (Sprint). 

First is the backlog board, which speaks for itself, it’s a visual representation of the work that we will be working on in upcoming iterations. We have defined various columns, to separate Epics, Requests, Stories pending analysis, Stories ready for iteration and Technical Debt.

On this board we make estimates on stories points, in order to determine the amount of effort per story. We have defined points based on small / medium / large / xl, but used numbers 1 / 2 / 5 / 10 in order to do reporting and calculate our velocity.

Secondly we have an iteration board, which we fill with work during our planning session. This looks more like a traditional Kanban board, with columns Iteration Backlog, Waiting, Doing, Stuck in the Mud, Review and Done.
During the two week iteration additional work will be added to this board, like incidents, requests for help, ad-hoc meetings etc. Through burn-down and burn-up charts we can keep track of the progression of the workload.
A more in depth look at how we have setup this board, with labels, tags and point will be provided in a separate blog post about the reporting.


###Reporting
We are able to get our reports from Trello to a Google sheet, by using the Trello api and Google script. 

![Burn Chart](/images/burn-chart.png "Emxample Burn-Chart") 
{: .pull-right}
We are able to create nice charts and share these with the relevant stakeholders as well. We use the Scrum for Trello plugin (link) to give points to stories, these point are collected in the script we have created.

If you are interested in how we managed to pull and store data from Trello, please read our detailed post about the script we created.

###Chat/IM
To keep in touch with each other we use group instant messaging, at the moment we use [HipChat](http://www.hipchat.com) from [Atlassian](http://www.atlassian.com). We have several rooms in HipChat and we have it open all day long actually. We also have a public room, we use as a “consultation” room for other teams who want to discuss something with us or have simple request. We have to admit we all <3 HipChat and it is getting bigger within our company. Especially after we automated the user management, of which you can find the code on github here.

###Travels
We also travel regularly to these office to meetup with the team and also collaborate with other teams. We recently organised a hackathon in Dordrecht, of which we will blog about soon :-)
We are already planning to do another hackathon, together with some developers, in London this time around.

So you can find us frequently in one of our offices, but we also attend interesting events and meetups. The next event we will go to is most likely [DevOps Days in Amsterdam!](http://devopsdays.org/events/2014-amsterdam/) Next month we will host our very own DevOps Day in our London office!!

See you somewhere soon :-)

	

