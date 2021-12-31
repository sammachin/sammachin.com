---
author: sammachin
date: 2015-01-01 14:08:06+00:00
draft: false
title: Train Ticket Machines - What about the Power Users
type: post
url: /posts/train-ticket-machines-what-about-the-power-users/

---

[![AdUnlnOCQAAnPLs](http://sammachin.com/wp-content/uploads/2014/12/AdUnlnOCQAAnPLs.jpg)
](http://sammachin.com/wp-content/uploads/2014/12/AdUnlnOCQAAnPLs.jpg)

Plenty of articles have been written on the UX of train ticket machines, while they tend to vary by train operating company they're usually one of 2-3 varients and usually generally awful to use!

I'm sure in plenty of the meetings where people design (I use the term loosely) the interface for these machines they are concentrating on making it as easy as possible to find the ticket for your journey, that is they are starting off with a use case of search and then taking on the purchase at the end of the process. For certain users this is probably a good way to go, I know where I want to go so now help me find a ticket for that, then let me buy one.

But what about another group of users, for want of a better term I'm going to call these people power users, they people that travel by train regularly, usually as a commute, they probably do the same selection of 3-4 journeys 50 or so times a year, They don't travel frequently or regularly enough to buy season tickets but they certainly know the system and know what ticket they want. Also they probably know the cheapest ticket for their specific circumstances, many people will be aware of certain 'hacks' on the train ticketing system like split fares and boundary zone tickets that can save you quite a lot on regular trips. Equally these people don't plan ahead they just want to turn up at the station and get a train, they don't pre-book tickets all the time as they need the flexibility. I was one of these people in fact I probably still am, for a while I was traveling a lot on trains, the photo at the top is my collection of used tickets from about a 6 month period. So I've used these machines enough to say I'm qualified.

This is where the problem arises, I want certain 'special' ticket options on a regular basis, every time I goto London I get a split fare at Didcot as it saves me £30 or so, do that 3 times a week and it adds up, so I usually ended up having to go into the ticket office and speak to the nice lady in there, at one point I was doing it so often that she got to know me enough to just ask 'the usual'. However what happens when these ticket offices are closed or worse have an enormous queue of tourists wanting their hand held through the whole process. Then us power uses get the raw end of the deal, we either end up wasting ages in a queue or more often than not over pay when we know we didn't need to just to get a ticket from the 'Fast Ticket' machines.

My friend Kevin Prince's experience with First Great Western this morning captures this perfectly:

https://twitter.com/kevinprince/status/549497550353735680

What was even more surprising was one of their replies:

https://twitter.com/FGW/status/549500102055043073

Yep thats right, they're blaming the technology, its the classic British '[Computer says No](https://www.youtube.com/watch?v=AJQ3TM-p2QI)' scenario, and thats the sort of thing that really winds me and most other technology professionals up no end, This answer really isn't true, its not they 'can't' sell special tickets its that they've chosen not too, given that its a computer in the ticket office that does allow then to sell these other tickets there clearly isn't a barrier in terms of technology, its just that they think the system to sell special tickets is so special and complex it must be guarded but their own staff and we can't let the mere mortal customer near the precious ticket computer. Or the cynic in me says they don't want to make it too easy to buy these special tickets or they fail to make quite such large profits as they currently do, but lets be generous and assume they're wanting to make things 'easier' for us.

Lets consider a few options:

1) they could just expand the current ticket interface with all the various stations and special ticket options, hopefully this has been thought about and somewhere a desicion was made to leave some of these more 'obscure' ones out in the name of keeping it simple for the person that buys one ticket a year. Ok not gonna go into this argument, lets move on.

2) They could expose the same interface as the ticket office staff have via a small 'advanced mode' button on the top of the screen, it would certainly be a fairly easy fix, not much new design but that does run the risk of confusing the untrained user if they somehow manage to press that button, its not like this is some sort of guided missile system, if users get lost and press the wrong button its not gonna kill anyone but if you've ever been stuck behind a person at the ticket machine who can't figure out the current interface this isn't a good thing either.

3) They could of course  simplify the fare system, introduce contactless payment, do away with tickets and use credit cards directly but thats a major undertaking for the whole rail network and of course it will almost certainly mean that these hacks us power users know to save money are lost and we'll end up paying more.

So we're left with a requirement to keep the existing ticketing and pricing models, and not hinder the current system for untrained users, Most of the ticket machines already have 2 modes, there's a 'Buy Tickets for Today' option which then takes you into the minefield of searching for your stations, or there's a 'Collect prepaid tickets' for picking up tickets that you bought online. My idea is for a 3rd 'hybrid' of these 2 options, I'm calling it Turbo Tickets.

The idea is that every possible ticket in the UK rail network has a code, its  something like 3 sets of 4 letters, so SYAT-SBRI-SADR That would be from Station YATton to Station BRIstol for a Standard Anytime Day Return, all UK stations already have 3 letter codes those of us that use the traintimes apps regularly probably know their frequent ones anyway, Other types like travel cards could replace the station codes so TFGW-FTAB-SATC could be a Travelcard on First Great Western for a Freedom TravelCard Zones A-B, as a Standard Anytime TravelCard. The point is that these codes don't have to be that easy to understand there would be a certain amount of logic in the system just to re-sue existing codes and let people learn patterns, but the scenario doesn't really require that, you could simply give every ticket type a 16 digit number, the idea is that if this is the ticket you buy regularly you'd learn the code, or have it written down then you just tap that into the machine and pay, boom out comes your ticket. There are various ways people could discover these codes, all outside of the ticket machine itself, Train companies coudl add them to their websites so when you search for a journey and price there's the code next to it, also you could print the code on the bottom of every ticket sold, so once you've bought a ticket once its easy to take an old ticket to the machine and tap in the code for the 'same again please'. Now there are some options these code might not work for, the main one I can think of is advance tickets, where you specify a certain train and usually get a booked seat, but that use case is already covered, most people buy those online or over the phone and pickup from the machine using a one time code already. The other thing that might need adding to the code is some way to specify a day perhaps a 4th block with the date eg 2312 for 23rd Dec, but to start with we could just use this system for tickets that are valid today. thats the use case, people that want to travel now and know what they want.  I've mocked up what the interface could look like one the ticket machine below:

[![Screen Shot 2014-12-29 at 11.59.40](http://sammachin.com/wp-content/uploads/2014/12/Screen-Shot-2014-12-29-at-11.59.40.png)
](http://sammachin.com/wp-content/uploads/2014/12/Screen-Shot-2014-12-29-at-11.59.40.png)




