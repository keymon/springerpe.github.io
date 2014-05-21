---
author: keymon
date: 2014-05-21
title: 'The other side of a technical assessment'
category: process
layout: post
image: 
  feature: DevOpsDaysLogo.png
published: true
tags: recruiting kanban assessment
comments: true
share: true
---

Have you ever though that your technical assessment can help you to attract the right people?

Early last year I took a more active role in the recruiting process for a Systems Engineer - [sadly aka DevOps Engineer](http://www.infoq.com/news/2014/03/devops) - for the development team I was member of in [Springer](http://joinit.springer.com/). Specifically I was involved in the technical process, reviewing CV's and being part of the face to face technical interviews.

Soon I got myself in the skin of the candidates, and I recalled the multiple times I was on that side. One of the parts that I always found interesting was the *technical assessments*.

My personal view of the technical assessment
----------------------------------

Usually the main goal of these assessments is just filter out candidates to reduce the time "wasted" by your engineers and, maybe, provide some context for some questioning later. I also think that **prompt feedback is quite a fair point**, but IMHO these assessments are much more than that.

When I did these tests as a candidate I was wondering about the job, drawing a picture of how much they care about recruiting, how skilled more or less the team could be, which technologies they used or even how interesting the position could be. All of it just based on some technical tasks.

These tests are usually the very first contact of the candidate with the engineering team and **the candidate will also evaluate the position and your team based on these assessments**. With that in mind, the technical assessment is even more important than the job description. 

So, although by that date we were able to hire amazing people, we decided to put some effort creating [our very own assessment](https://trello.com/b/5qMF0d5A/springer-platform-engineer-assessment). 

So far the experience has been quite positive. And I would like to share with you the premises we followed, what we were looking for and our experiences in the last months.


"Running software over comprehensive documentation"
---------------------------------------------------

We are techy folks, and we look for techy folks, and techy folks like getting their hands dirty. Obviously, **we must ask to write code that actually works and that we can evaluate**. 

On the other hand we don't want them to spend time in tedious low value work so **we provide a working skeleton which works out of the box. This removes all the initial hassle and which provides the right context**.

Also, **the challenges and technologies should be relevant to the future position**, so one can get an idea of how the work will be. This does not mean include every possible tool and use case - for us that would be impossible ;) -, but just a representative subset.

For this we use [vagrant](http://www.vagrantup.com/) and some [chef-solo](http://docs.opscode.com/chef_solo.html) configuration that installs a scala webapp. You only need to install vagrant and run `vagrant up` to get a working environment. 



Learn the candidate's working style
-----------------------------------

[We use Scrum+Kanban internally]({% post_url 2014-05-10-how-we-work %}), and we want to learn the candidate's methodology and the steps they follow doing the tasks (thought I admit it's quite difficult). In that case **[Trello](http://trello.com) is the perfect tool to split and organize the tasks**. It also allows direct communication with the candidate using comments, and it is great to give them feedback in the reviewing.

Aditionally, using **[git](http://git-scm.com/) allows us to understand their working style and [care for details](http://bit.ly/1kmXUF3)**. We use [bitbucket](http://bitbucket.org) that gives free hosting for private git repos.




Space for fun, to learn and innovate
---------------------------------

We tried to keep it "fun" - in very geeky terms, ofc ;) - and make it an oportunity to learn, if that is the case. For that **the tasks should be small and simple, and include some clues to allow research for the right answer**.

In these cases I personally found it frustrating being restricted in time and to a specific set of skills. It's true we want skilled candidates who are able to solve problems quickly and under pressure, but we also value people who are able and willing to fill their own gaps. So even if your candidate does not have the skills (or they are just busy), **the test should encourage them to research, learn and demonstrate it, without any time restriction**. 

We give room for innovation, allowing them to propose any solution, enhancement or new idea, as long as they justify it. 

Some task examples
------------------

In [our specific assessment](https://trello.com/b/5qMF0d5A/springer-platform-engineer-assessment) we want to assess their knowledge about automation, so we use chef. For networking we include iptables and load-balancing. For troubleshooting, a performance issue in a scala webapp. We also want to see how they explain themselves, so we ask for technical feedback for the supposed development team of that webapp.


Keep it self containing 
-----------------------

Finally, recruiting is a marketing process. **You need to be able to share a simple link including all the required information** from the job description to the test itself. Then send it to twitter, forums, mail lists... In our case the [link to the Trello board](https://trello.com/c/XF1D9Rqw/1-read-this-first-job-description) and the [git repo](https://bitbucket.org/springersbm/systems-engineer-assessment/src/master/README.md) do it.

How was our experience?
-----------------------

So far the feedback was quite positive. Most of the candidates found it interesting and several of them confirmed that they actually got interested in the position mainly thanks to it. Two of these are currently working with us and I can tell you they are great professionals :). 

There was of course some good criticism: It might be too long and time consuming for somebody not familiar with the tools, but again: we want skilled people and people able to learn... and learning is never for free. In some cases there were some problems like not having access to a Linux/MacOSX box to run it, but we expect them to workaround such issues. Others didn't like the chosen tools (e.p. chef), but they are free to propose another stack if it's justified.

Also, some people didn't like being asked to do it before knowing more about the job and being sure it was worth it. To be sincere I still don't really know when is the right moment to ask to complete it, before or after a first interview.

Feel free to use it!
-------------------

Please feel free to use these ideas in your own assessment. If you are looking for a Systems Engineer, [as we do]({% post_url 2014-05-16-we-are-hiring %}), you can reuse this implementation, but **please change the tasks to fulfill**. For instance you can ask to use [docker](https://www.docker.io/) to build a deployment system, [dokku](https://github.com/progrium/dokku) for a simple PaaS, setup some specific service like an IRC server, fix some misconfiguration, use puppet...

For other positions, like developers, a codebase with tests and integrated with a CI system like [travis](https://travis-ci.org/) can do the trick. 

We are hiring!
--------------

As you can imagine, [we are recruiting]({% post_url 2014-05-16-we-are-hiring %}) for our Platform Engineering team in London and Berlin!!! ;)

So don't doubt to [check out our assessment](https://trello.com/b/5qMF0d5A/springer-platform-engineer-assessment). 

Of course, there are also [other open positions for other roles in Springer](http://joinit.springer.com/#join-our-team).

*-- by Hector Rivas (aka Keymon)*
