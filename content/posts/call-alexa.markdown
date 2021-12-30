---
author: sammachin
date: 2015-12-16 18:35:52+00:00
draft: false
title: Call Alexa
type: post
url: /call-alexa/
---

I've been doing a lot of stuff with the Amazon Echo and the underlying Alexa service which sits behind it. For those of you that don't know the Echo is a home 'appliance' about the size of a tube of Pringles, it sits in the home and responds to the keyword "Alexa" you can then ask it questions or give commands. Since Alexa was integrated with IFTTT as a trigger its opened up a whole world of fun integrations, especially to my various connected home devices, I can now say "Alexa Trigger Office Lights" and the LIFX bulbs in my office turn on or off, or Alexa TV off and the Harmony Hub will shut off my TV!

Anyway back to the hack, Amazon have opened up the Alexa Voice Service to developers so that it can be integrated into other devices than the echo, at this point its important to understand the difference between the Echo and Alexa, the Echo is the hardware and has additional features such as being a bluetooth speaker and is capable of playing audio content from Amazon and Audible, the Alexa Voice Service is really just the control piece so you still have things like the IFTTT integration but not the full echo functionality.
In addition the keyword detection of "Alexa" is part of the echo not the cloud service so as a developer you have to figure out how to capture the audio commands from the user.

The actual Alexa Voice Service API is pretty simple, in effect you send it an audio file of your command and it sends you back an audio file of the response. There's some additional meta-data but that can mostly be hard coded for the purposes of a hack.

Given that its just audio files going back and forth I thought this would be a nice thing to integrate with telephony, allowing me to call Alexa from my phone and issue commands even when I'm out of the house, for example via IFTTTT Alexa can control my Nest so now I can call and say "Trigger Heating" knowing the house will be nice and warm when I get home.

The first time you call Alexa from a new phone number you need to oAuth the app to access your Alexa account (you have all the same Alexa profile and service regardless of which device or service you use to access Alexa" So my app will see that its a new caller and tell you that its sent you a link to register via SMS, clicking on this link will take you to the Amazon login and auth pages which once complete will then return you to a (very basic) done page that reminds you of the link to manage your alexa service on the web.

Now whenever you call Alexa will answer and ask "What Can I do" just say your command, no need to start with the keyword "Alexa" as she's already listening. Things are a bit sub-optimal here, mainly because the server is recording a file and then posting that to my app, its using the silence detection feature to detect the end of the file but I think there's room to speed things up, you can also press any DTMF key after your command to stop the recording instantly. There's then a couple of seconds delay while the recording is posted to my app, the audio is converted into the format Amazon expects (16KHz, Mono, WAV) and then posted to the Alexa Voice Service. When AVS responds with audio thats then saved as a temporary file and is send back to play the response, considering the various round trips and conversions I'm amazed this works! but there's definitely scope to make it tighter.

Checkout the video below and if you want to try it for yourself you can call +44 117 200 1500 in the UK, usual disclaimers apply, this is very much a beta it might break or go away at any point.

UPDATE: If you want to revoke the permission to access your alexa account from this app then visit [https://www.amazon.com/ap/adam](https://www.amazon.com/ap/adam)

<iframe src="https://www.youtube.com/embed/XnNztJJbmUs" allowfullscreen="allowfullscreen" height="315" frameborder="0" width="420"></iframe>
