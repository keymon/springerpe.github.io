---
author: jorja
date: 2014-10-15
title: 'How not to get bitten by the POODLE on Mac OSX Chrome'
category: tech
layout: post
image:
  feature: DevOpsDaysLogo.png
published: true
tags: poodle hack macosx chrome
comments: true
share: true
---
Hello! 

Just a quick post on how to keep yourself from being exploited through (https://poodle.io/)[POODLE] if you're using Google Chrome on a Mac OSX. 

It's very simple, you can open Chrome via Terminal by typing: 
`nohup /Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --ssl-version-min=tls1 &`
This disables the use of SSLv3 in Chrome.

We have another solution, though. You can use Automator to create a launcher:

1. Launch Automator from Applications
2. Select ‘Application’ and click ‘Choose’
3. Select 'Library' > ‘Utilities’ from the left column
4. Double-click ‘Run Shell Script’ to put it in the workflow area
5. Replace "cat" with `open -a "Google Chrome.app" --args --ssl-version-min=tls1` and make sure it passes the input to stdin
6. Save the workflow as an Application (I saved mine as 'Chrome - Poodle' in my applications folder)
7. Close Chrome
8. Double-click on the new Chrome launcher you just made

You should now not be able to see "Warning! If you see this box, your browser supports SSLv3!" when you go to (https://poodle.io/)[poodle.io]
