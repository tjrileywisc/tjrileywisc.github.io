---
layout: post
comments: true
title:  "Candlestick app update"
excerpt: "Learning about Android intents"
date:   2015-06-01 12:00:00
---

This block of xml in my app's android manifest is preventing me from making calls when my app is installed. 
I assume its intercepting all outgoing call requests via the intent. I'll need to comment it out while I work on other parts.

<pre>
            &lt;receiver android:name="OutgoingCallHandler"&gt;
                &lt;intent-filter&gt;
                    &lt;action android:name="android.intent.action.NEW_OUTGOING_CALL" &gt;
                    &lt;category android:name="android.intent.category.DEFAULT" &gt;
                &lt;intent-filter&gt;
            &lt;receiver&gt;
			
</pre>

<p>
EDIT: found the problem was the NEW_OUTGOING_CALL part of the intent, removed that. It's obvious to me know what was happening;
whenever I had the app on the device it would listen for an attempt to make an outgoing call and take over.
</p>

Found some very helpful code at http://www.mkyong.com/android/how-to-make-a-phone-call-in-android/ that allows me to call
a specific phone number from the app, skipping the OS dialer (I won't need it for this project since I'll eventually be using
the hardware rotary dial on the candlestick phone). Now the code is in my bluetooth loop so it won't allow the call 
until it finds a device called 'Candlestick' among visible paired bluetooth devices.