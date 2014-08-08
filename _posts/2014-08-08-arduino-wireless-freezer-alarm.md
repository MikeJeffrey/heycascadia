---
layout: post
title: Making a wireless freezer alarm with Arduino
comments: True
---

The other day I opened my deep freeze to discover everything inside slowly melting.
The freezer had tripped the GFCI on the circuit, and silently turned off.

I don't keep a lot of food in there, so there's no real reason for a freezer alarm
that will ping me when the temperature rises, but it was a great excuse to buy and
tinker with an Arduino.

Here's where I'm at so far:

<img src="/images/IMG_20140807_094658119.jpg" width="600px">

<!--more-->

It's composed of:

* An [Arduino Uno](http://www.amazon.com/gp/product/B00BT0NDB8/ref=as_li_tl?ie=UTF8&camp=1789&creative=390957&creativeASIN=B00BT0NDB8&linkCode=as2&tag=camperizecom-20&linkId=MFPBW5NMRVYH2KDN).
* A [CC3000 wireless shield](http://www.amazon.com/gp/product/B00J2QA9FE/ref=as_li_tl?ie=UTF8&camp=1789&creative=390957&creativeASIN=B00J2QA9FE&linkCode=as2&tag=camperizecom-20&linkId=QXHSANCOQFYV3OO7).
* A [DHT-22 temperature and humidity sensor](http://www.amazon.com/s/?_encoding=UTF8&camp=1789&creative=390957&field-keywords=dht-22&linkCode=ur2&rh=i%3Aaps%2Ck%3Adht-22&sprefix=dht-2%2Caps&tag=camperizecom-20&url=search-alias%3Daps&linkId=K6KTTIZADGHF3SAQ).

*(Oh, by the way: [you have to solder Arduino shields!](http://www.heycascadia.com/2014/08/08/you-have-to-solder-arduino-shields/))*

Thanks to my colleague Dave Par's [wifi weather station](https://github.com/Davepar/wifi-weather-station)
code, I had it up and running pretty quickly. The code reads the temperature and humidity every three
minutes, and sends the data to [dweet.io](http://dweet.io).

The next step is to turn that data into an alert. I've tried textbelt.com, so far with no luck; my next
idea is to have an App Engine app polling the data and emailing me if the temp passes a preset level.

More to come.
