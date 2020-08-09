---
author: sammachin
date: 2017-08-07 11:58:56+00:00
draft: false
title: Echo Show Security Camera with a Pi
type: post
url: /blog/build-your-own-rasp-pi-security-camera-for-the-echo-show/
categories:
- Blog
---

![](http://sammachin.com/wp-content/uploads/2017/08/FullSizeRender-2-290x300.jpg)

The Echo Show is the first Alexa enabled device from Amazon with a screen, with this device Amazon introduced some new capabilities within the Sklls SDK particularly around video, one of these is the ability to view home security cameras such as the Nest and the Ring Doorbell using the command "Alexa show X camera"

However these devices are all at the pricy end of the home camera market, I do like having a few cameras around the house mainly so I can checkup on what chaos the dogs are causing downstairs when I'm working up in my office. However fitting out my house with enough Nest cams to cover most o the areas would be running close to £1000. 

I've used the cheaper Motorola Scout camera before and that worked pretty well, it can be picked up for about £50, but then I got thinking about the Raspberry Pi, specifically the Pi Zero W that was released a few months back, we now have a very cheap very small device that has Wifi and an interface to add an internal camera, you therefore have all the hardware you need to create a compact security camera. 

There are plenty of articles around the web on how to setup a Pi as your own home security camera however the Echo Show has some fairly particular requirements around the format of the video steam, especially the transport layer, it requires RTSP over Interleaved TCP connection on port 443 secured with a TLS cert! Don't worry if this all sounds a bit scary I've done the hard work digging into this so you don't have to.

Right now this is quite a complicated process with many steps covering lots of different areas so its only really  suitable for the more advanced hacker, I'm hoping to simplify several steps into a single script in the future, Pull Requests are welcome.

Checkout the video below and if you want to build your own then the instructions and code are all on [GitHub](https://github.com/sammachin/camerapi)
<iframe width="560" allowfullscreen="None" src="https://www.youtube.com/embed/mPnFFOyw8pM" frameborder="0" height="315"></iframe>

