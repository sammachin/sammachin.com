---
author: sammachin
date: 2016-01-03 16:05:30+00:00
draft: false
title: The $10 Echo
type: post
url: /posts/the-10-echo/
---

For the 3rd instillment of my "Putting Alexa on all the Things" series I've got Alexa up and running on a [CHIP](http://getchip.com).

For those of you that don't know the CHIP is a bit like the Raspberry Pi, it’s a small, cheap ARM based computer that runs linux and has some input/output pins, I backed the CHIP on kickstarter last May time and had kinda forgotten about it until they turned up in the post on New Year’s Eve :) I also just picked up a Raspberry Pi Zero but for this project the CHIP seemed like a better platform and it was a good opportunity to try it out. The advantages of the CHIP over the Pi zero are that it has onboard WiFi and a built in audio in/out interface (with a small mod) The Pi would have required USB adaptors to have WiFi and the Mic in working along with needing a memory card so although the Pi Zero is $5 and the CHIP is $9 in total BOM the CHIP works out cheapest.

The CHIP came pre-installed with a custom build of Debian on its built-in 4GB storage, (taking about 400MB leaving plenty of room to work) Out of the box it has composite output and comes with an old school phono cable so I hooked it up to my TV and plugged in a USB keyboard and mouse which got me booted to a typical desktop, from here I configured the WiFi to connect to my home network, checked the IP address and then confirmed I could SSH onto it. Once all that was done I could unplug it from the TV and I wouldn't need GUI access any more, (you can also install a VNC server if you need to get back to the GUI later) 
The CHIP uses a TRRS 3.5mm jack on the board to interface to audio and video devices, if you want to use this connector as the Mic input it involves a small mod to the underside of the board, slicing through a track with a stanley knife and then putting a blob of solder across the 2 pads, you've now lost the composite video out but gained mic in (hence my setting up the wifi before the HW mod!) Both the composite video and the mic in are available as pins on the breakout headers so if you need to connect to those at the same time or after the mod its still easy, thats about all the hardware work needed here, now it's just plugging stuff in and software.

I wrote the alexa application in Python, I'm using alsaaudio to record sound from the mic input then the same code that I used for my last 2 alexa hacks to pass it to the Alexa Voice Service. Because I have total control of the recording code this time I didn't need to do any transcoding into the wav format required by AVS I could just record and post directly. AVS responds with an MP3 rather annoyingly so I also had to have something to play that out, the simplest option was to install mpg123 and then play via a system command, a bit hacky but it works.
The current implementation doesn't have the keyword detection of the echo (indeed I think implementing it on your own device is against Amazon's T&Cs;!) so I attached a button to one of the GPIO pins on the CHIP, currently CHIP doesn't have a python library to interface to its GPIO and I didn't fancy getting down and dirty with C so I hacked it to poll via the filesystem, again rather ugly but seems to work. 
So now you press down the button speak your command to alexa and wait for the response to be played back :) I quite like this UX, I'm tempted to try and find one of those old retro style desk intercoms that businessmen had on their desks in 80's films and put the board in that, then I can have Alexa as my PA on my desk :D

I've posted the code for all this on my [github](https://github.com/sammachin/AlexaCHIP) along with an attempt to document how to set yourself up one, if anyone fancies porting to the Raspberry Pi it should be easy enough, just the GPIO stuff to refactor I think please send me a pull request. In terms of additions I'd like to add an LED or two so you can see the status but I think I'll wait till CHIP have a proper GPIO library for that. 
As usual checkout the demo video below :)
<iframe width="560" allowfullscreen="None" src="https://www.youtube.com/embed/Z1HGJyfoUBE" frameborder="0" height="315"></iframe>
