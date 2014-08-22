---
author: otte
date: 2014-08-22
title: 'Process or no process'
category: process
layout: post
image: 
  feature: cocktails.png
published: false
tags: team bullshit devops agile distributed
comments: true
share: true
---

So here's a common situation and I do not have the solution....

Imagine you work in a large organisation, 5000+ employees (forgive me if you think this is small). You have various IT teams across the board and they all do technical stuff, they are scattered across countries even continents. To get there stuff done they need various tools, services and equipment.

They all want to be able to move fast and you are looking to avoid bureaucracy so you do not end up in endless procedures and request forms. Various attempts to centralise certain tasks resulted in quite some resistance so this does not seem to work quite well… So we try to give complete freedom to the various teams, so they are able to move more independently and get stuff done themselves quickly. But in several cases, this results in a lack of ownership in the long run and eventually quite a messy situation, so this seems no good either. 

Let me give you an example of something that happened recently in a team with a lot of freedom:

A development team in country X is using an SSL certificate in a part of the web app they were developing. It was too cumbersome to request to get it from another operations team, that already was handling certificates team (and located another country) and there was not a clear process, so they purchased it directly through a credit card of one of the employees. They were inexperienced, and got a lot of trouble but eventually they were all good to go and moved on. Of course the work done was not really documented, as there were other priorities.

But then some years later, it bites you in the ... All people who work on this do not longer work for the company, the certification authority sends warnings to a canceled personal email account,  the credit card used is expired or just canceled the payment and certificate just gets revoked. 
Even worse: there is not a clear process of how the certificate must be updated, how the software uses it, etc. Just some notes in a README file. Nobody has experience with it, and the people who did it before are not here anymore… So a complete mess.

So in this case what do you do, there are more teams in this big company who all need some certificates sooner or later and will have the same issue. There are tons of other examples like this in large organisations, where it’s so simple for teams to arrange stuff by themselves like hosted git repos, chat tools, AWS, RackSpace etc… 

Luckily there’s always a few people you can always count on to fix these issues when they arise, but that cannot be the answer to this problem.

How do you give teams a quick and easy way of working and at the same time prevent chaos and duplication of efforts and resources..without introducing “bureaucratic” request procedures that slow everything down?

We tried several things and I have not found the perfect mix yet, but will keep looking and trying.
Advice is always welcome.
 
Cheers!
