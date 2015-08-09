---
layout: post
comments: true
title:  "Candlestick app update, char-rnn"
excerpt: "Updated the notification code in the app, discovered char-rnn and Docker"
date:   2015-06-30 12:00:00
---

# Modifications to candlestick app

Got some time to work on the app this evening. Moved the notification code out of the onCreate method of the main activity and into the
background service instead (it feels more correct there). The service appears to be starting correctly but I am now trying to change the
notification text so that it changes when a call comes in (I think that was working at one point) and also the behavior will be different
when you tap on it, depending on whether or not a call is actually coming in at the moment.</br>

# Docker containers and char-rnn
Also have started to get a Docker container running Ubuntu and Torch so that I can play with <a href = https://github.com/karpathy/char-rnn>char-rnn</a>
It's working as expected according to that page. I'm training a dictionary now that I found on Project Gutenberg to see how that will behave. 
It would be interesting to see if any of the suggested definitions make any kind of sense.
