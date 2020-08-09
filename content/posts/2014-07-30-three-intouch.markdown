---
author: sammachin
date: 2014-07-30 15:48:34+00:00
draft: false
title: Three InTouch
type: post
url: /blog/three-intouch/
categories:
- Blog
---

I've been lucky enough over the past few weeks to trial Three's InTouch app, which allows you to make and receive calls and SMS on your phone over WiFi, ideal for times when you don't have coverage.
I was particularly interested in trying this out as when I used to work at O2 I was part of the small [team](http://thelab.o2.com) that created this concept in [O2 Connect](http://news.o2.co.uk/2011/11/02/o2-connect-making-calls-and-texts-simple/), which went on to launch as [Tu Go](http://tu.com/en/), so having spent many hours thinking about the various ideas in the product I was keen to see what Three have done.

The basic concept isn't really that hard to understand, its an app that works like your normal voice & sms apps but uses WiFi, however there's a fair few behind the scenes things to work out and some of the assumptions of telephony suddenly change when you have multiple apps.
In general the Three product is very good, I think its a white lable partnership with Mavenir Systems but thats pretty typical for a telco, they're far more a buy then build type of outfit.

I've been testing the app on my Nexus 5, I had a little trouble at first as the app won't run if your device is rooted which is highly annoying but to be expected from a telco, I'm reliably informed that rootcloak will get around this.

Registration is done via the mobile data network, this does mean you need some signal the first time you use it but thats pretty hard to avoid as there is really no other way to verify your number for most carriers, the benefit of this method is that there is no username or password to remember thats all internal to the app, however the big drawback here is that it means the app only works on a single device, and thats the one that has your SIM in it. With O2 Connect (and TuGo) one of the key features for us was that you should be able to use your mobile service on any device, e.g. your iPad. And I'd really like to see Three add support for this in a future update.

On the Android version the app does a nice job of pulling in your call history and SMS from your existing apps so all your messages are in the single place, however if you then send a message from the app it isn't synced back into messages. This is a really hard problem to solve for a lot of devices as in general apps can't write to the message app, esp. on iOS. In the carriers ideal world you would just use their app for all your SMS and then its in one place, however fragmentation is bound to occur in the real world.

Similarly the voice service has the same issues with the call history, one feature I found that I'm really missing from my native Android dialer when using the Three app is the CallerID by Google where most company names are auto added even if they aren't in my phonebook, still this is kinda an edge case and just something to live with, I don't think Google provide an API to their callerID lookup anyway.

The other drawback is that the app doesn't alert my pebble with incoming calls and SMS the way that the native apps do, again kind of an edge case and hard to say who should fix it but it all adds up to just making the app not quite feel like a first class phone service.

There is one feature that Three have added which I am seriously impressed with though, the ability to select which WiFi Networks will be used for In Touch, this is seriously neat as it means that I can just enable the places that have no three service but when I'm somewhere that has good network signal I can still use WiFi for data, this single feature alone overcomes a lot of the limitations above as it means I can truly use it as a backup for calls and texts rather than having it take over.

I've also had a brief play with the app on my iPhone, in general it seems to work very nicely and has mostly the same setup, there's no pulling of SMS and Call History from the native apps but this is a limitation of iOS so I'll let that slide, they even managed to keep the 'allowed hotspot' feature, which I didn't realise was possible with iOS but thanks to [Adam Cohen Rose](http://twitter.com/adamcohenrose/status/494493231132844032) for pointing out how it can be done, and [Simon Maddox](http://www.simonmaddox.com/) for the [test implementation](http://https://github.com/simonmaddox/ios-get-current-wifi-ssid)

All in all I'd say its about 4/5 have to deduct one point for the lack of multi-device support but what is there works really well. I'd recommend installing and setting it up now so next time you find yourself without signal somewhere you're ready!

Links are [Play Store](https://play.google.com/store/apps/details?id=com.hutchison3g.threeintouch) and [App Store](https://itunes.apple.com/gb/app/three-intouch/id895812887?mt=8)

[metaslider id=198]
