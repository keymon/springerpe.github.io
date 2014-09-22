---
author: jorja
date: 2014-09-22
title: 'Trello Iteration Reporting Script'
category: tech
layout: post
image:
  feature: DevOpsDaysLogo.png
published: true
tags: trello springer tools reporting scrum google-apps-script
comments: true
share: true
---
We, here at platform engineering, love transparency and exchanging information — this is why we started creating spreadsheets reporting the workload of the team based on our Trello iteration boards. We initially started doing this manually, however, this is horribly tedious! As tech people, it is only natural (and necessary) that we find a solution that automates this task.

###Go Big or Go Home

![Anatomy of our Trello board]({{ site.url }}/images/anatomyoftrelloboard.png)

First step was finding tools that other developers have created. There are some that do generate reports (e.g. burndownfortrello.com), but they did not meet the requirements of the team. With the addition of using [Scrum for Trello](http://scrumfortrello.com/) and hashtags, our Trello boards are not the simplest. This makes it more difficult to get what we wanted from the existing options. We wanted to create a whole spreadsheet that included sheets for a burn up - burn down graph, completed work breakdown pie chart, total vs done bar chart, and a lot more. We obviously do not do things half-heartedly over here, so what else was there to do but create our own [Google Apps Script](http://www.google.com/script/start/)?

###Google Apps Script

According to its [page](http://www.google.com/script/start/), “Google Apps Script is a JavaScript cloud scripting language that provides easy ways to automate tasks across Google products and third party services and build web applications.” Google also provides [fantastic tutorials](https://developers.google.com/apps-script/articles) on how to basically make Google your spreadsheet-making email-sending super robot. Making Google connect to the Trello API to create Google Drive spreadsheets with the content we wanted? This sounded like Christmas to us!

###Trello Iteration Reporting Google Apps Script

We have created an apps script that collates data and creates the following data sheets based on the Trello cards:

![Iteration details]({{ site.url }}/images/iterationdetails.png)

- **Iteration Details**
  - Calculates the story points for each label in each list

![Daily status]({{ site.url }}/images/dailystatus.png)

- **Daily Status**
  - Calculates the daily story points based for: Left in Iteration, Work in Progress, Completed Work

![Hash Tags Data]({{ site.url }}/images/hashtagsdata.png)

- **Hash Tags Data**
  - Lists the hash tags used in cards and the equivalent total story points for each hash tag

After creating the data sheets, the script then creates the following charts:

![Total vs Done]({{ site.url }}/images/totalvsdone.png)

- **Total vs Done**
  - A bar chart that compares the total story points and completed work for each label. This is based on the Iteration Details sheet.

![Total Work Breakdown]({{ site.url }}/images/totalworkbreakdown.png)

- **Total Work Breakdown**
  - A pie chart that represents the percentage of each label for the total work to be done in this iteration. This is based on the Iteration Details sheet.

![Completed Work Breakdown]({{ site.url }}/images/completedworkbreakdown.png)

- **Completed Work Breakdown**
  - A pie chart that represents the percentage of each label for the completed work in this iteration. This is based on the Iteration Details sheet.

![Burn Up - Burn Down]({{ site.url }}/images/burnupburndown.png)

- **Burn Up - Burn Down**
  - A line chart that graphs the story points for: Left in Iteration, Work in Progress, Completed Work. This is based on the Daily Status sheet.

![Hash Tags Points]({{ site.url }}/images/hashtagspoints.png)

- **Hash Tags Points**
  - A bar chart that compares the hashtags based on their story points. This is based on the Hash Tags Data sheet.

Finally, the apps script is open source, because we believe that the best technologies are products of collaboration.

We felt your excitement building while reading through this blog post, so without further ado, we present to you… the **[Trello Iteration Reporting apps script](https://github.com/SpringerPE/trello-iteration-reporting-apps-script)**!

This is the part where you freak out and celebrate :)

![Freak out!!](http://i1254.photobucket.com/albums/hh608/breatheonme85/oprah_favethings.gif)



