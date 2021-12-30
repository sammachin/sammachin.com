---
author: sammachin
date: 2015-12-17 12:06:42+00:00
draft: false
title: Alexa in the Browser
type: page
url: /alexa-in-the-browser/
---

Following on from my previous [hack](http://sammachin.com/hacks-and-projects/call-alexa/) allowing you to access Alexa from your phone with Twilio I present Alexa Web, accessing Alexa via your web browser.

This hack was actually started before the Twilio one but I wanted to get that out first, this started life as part of our entry for the [Braintree BattleHack world finals](https://2015.battlehack.org/finals) last month in San Jose, that was a fairly simple implementation of the Alexa client in a browser with some other push related features, Now I've stripped those out and polished it up into its own app.

Much like the Call Alexa hack you need to grant permission to access your alexa account but this one is a little more responsive and better quality, you can leave the window open all day in the background and just click when you want to issue a command to Alexa, you don't need to use the alexa keyword just click the page and hold down your mouse while you are speaking a bit like a walkie-talkie.

The coloured circles will give you some visual feedback on whats going in, light blue is listening/recording, dark blue is thinking, green is playing the response and a red flash indicates an error, while is in standby the circle is white so generally pretty similar to the echo hardware itself.

There's also a thread over on [reddit](https://www.reddit.com/r/amazonecho/comments/3x498e/talk_to_alexa_over_your_phone/) discussing my call alexa hack and I'll post this one as a new thread there too where you can ask any questions.

I've found this really useful for testing out alexa integrations and developing new skills as I can have it open on my desktop and not have to shout to the echo downstairs, its also another option for accessing alexa when you are out if you have an android phone.
The app uses some serverside javascript to capture the audio with getUserMedia so you'll need a webRTC capable browser, (Chrome, Firefox, Opera and Edge no Safari and nothing on iOS) then posts that to my app running on Heroku which handles the conversion and sending to the Alexa Voice Service then sends back the response.

As usual checkout the video below and if you want to try it out goto [https://alexaweb.herokuapp.com ](https://alexaweb.herokuapp.com)

UPDATE: If you want to revoke the permission to access your alexa account from this app then visit [https://www.amazon.com/ap/adam](https://www.amazon.com/ap/adam)
<iframe width="420" allowfullscreen="None" src="https://www.youtube.com/embed/zSUXjpljM84" frameborder="0" height="315"></iframe>
