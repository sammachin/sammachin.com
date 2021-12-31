---
author: nav9ok
date: 2014-07-13 21:18:25+00:00
draft: false
title: Twilio to Sonos via Heroku, Pusher and a Pi.
type: post
url: /posts/twilio-to-sonos-via-heroku-pusher-and-a-pi/
---

Over the easter weekend I was looking for an idea of something to build, somehow I came up with the idea that it would be kind of cool to be able to make 'announcements' around my house when I'm not there, not really sure why but I'm sure there's some use case for this when combined with a home security webcam or maybe I can just talk to the cats.

Anyway the basic concept is that I can call a number hosted on [Twilio](http://twilio.com), that will play a short announcement and then allow me to record a message, much like classic voicemail so far, now the cool bit! Once that message is recorded twilio calls an application I'm running on [Heroku](http://heroku.com), that in turn fires a pusher event which is picked up by a second application this time running on a [RasberryPi](http://www.raspberrypi.org/) at home, this Pi application will take the data from the pusher notification  specifically the URL on twilio's servers which has the voice recording. The application then uses this a sonos library to discover all the active [sonos](http://sonos.com) devices on my network, group them into a single player and then tell the sonos to play the recording. The result is my voice message played out throughout the house!

Ok so its not exactly the most useful of household services but it was an interesting little hack in terms of hooking things together, I certainly used a lot of platforms and technologies. Who knows maybe someone will find it useful in an office environment or something, the Play 1 is now a pretty cheap sonos device so it could almost be worth it even if you just needed a remote tannoy system.

Video of it in action is below and I've put the code on [GitHub](https://github.com/sammachin/twiliopaging)
<iframe src="//www.youtube.com/embed/838V259GREI" allowfullscreen="allowfullscreen" height="315" frameborder="0" width="560"></iframe>
