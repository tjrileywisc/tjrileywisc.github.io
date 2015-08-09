---
layout: post
comments: true
title:  "Candlestick app update"
excerpt: "Implemented background service in Candlestick app"
date:   2015-06-28 12:00:00
---

# Modifications to candlestick app
I was finally able to make some small progress on the app after distractions of machine learning and moving the past couple of weeks.</br>

Now the app has a running service and has a notification that changes when an incoming phone call is received. Still need to do some updates to
watch the actual current call state and update the notification. When a call comes in, it should allow the user to start a specific activity that
just has two big buttons; take the call on the phone you are holding, or send it to the phone. That activity launches, but I'll need to send
something via bluetooth when the second button is pressed to pass the call.
