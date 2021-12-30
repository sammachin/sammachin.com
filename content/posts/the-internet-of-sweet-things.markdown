---
author: sammachin
date: 2016-01-03 18:48:51+00:00
draft: false
title: The Internet of (Sweet) Things
type: posts
url: /posts/the-internet-of-sweet-things/
---

The Friday before Christmas was the Christmas Party at the Pervasive Media Studio in Bristol, Unlike most office parties which involves a couple of boxes of cheap wine and drawing some holly on the meeting room whiteboard The Studio encourages residents to all create something interesting, there's usually some silly games, creative art and assorted tech projects that people have put together, its more an end of term at school feeling than your typical office party! This year I wanted to do something, and as its my current top toy, use the Amazon Echo. 

I came up with the idea of an IoT enabled candy dispenser activated by the echo possibly with a small game into the mix so you play the game against Alexa and if you win then you get some M&Ms; from the dispenser. As it happened most people were happy enough with the voice activated sweet dispenser so we put the game to one side and I'll write that up separately.

So back to the hack, first I needed to find a sweet dispenser that was suitable hackable, I'm really not very skilled with materials and craft so avoiding doing anything mechanical was a requirement, after searching a few of the High St novelty/gadget stores and coming back empty handed I finally found one on Amazon that looked likely, the [Elgento Motion Activated Candy Dispenser](http://www.elgento.co.uk/automatic-candy-dispenser.html) And available on Amazon Prime as obviously I'd left this till the last minute! (PS I have now found that Robert Dyas have these in the UK and as of Jan 2016 they're selling for £9.99! might pickup a spare) I figured that should have the basic parts I needed and I could hopefully hack the motion sensor to activate it in another way.

When it turned up I set about taking it apart (after testing it worked before I set to it with my tools) I was pleasantly surprised as to just how hackable this was, I was expecting a sub £20 novelty to be glues together and pretty hard to take apart without damaging things, however this was all small screws and once I'd got into the main mechanism under the sweets try I found a couple of small circuit boards, one for the IR sensors, one for the power switch and a which was the control and timing circuits this was then wired to a small motor which via a gearing drove a screw wheel to dispense the sweets. 

After poking around with a multimeter and shorting a few points I figured that the simplest method was to remove all the electronics and just keep the motor and mechanical parts. There was a nice hollow tube on down to the base and even a cutout on the rear which allowed me to take the wires from the motor down and out the back of the unit. Once putting things all back together I now had a dispenser that would churn out sweets whenever I applied 5V to the wires coming out of the back, perfect!

For my new control hardware I used a Particle Photon board and a small Solid State Relay from Maplin (I could have used a regular relay but this was the cheapest in stock) I worked out that to deliver around 5-7 sweets the motor needed to be on for 2secs, any shorter and the user might get nothing and too long would risk the motor getting hot. So a simple bit of code on the photon to have a function take a pin high for 2 secs and then wiring that pin to the input of the Relay with a new 5V usb power supply through the relay to the motor. 

The Particle boards also have the advantage of being integrated to IFTTT so I now had the ability to call my function to drive my motor all from any IFTTT event, also Alexa can be setup as an IFTTT trigger with your own custom keyword, so without even needing any of my own server side code I now have a voice activate M&M; dispenser!

Checkout the video of Sienna demonstrating the setup at our Christmas Party below.


<iframe width="560" allowfullscreen="None" src="https://www.youtube.com/embed/ei_BbkTW3pA" frameborder="0" height="315"></iframe>
