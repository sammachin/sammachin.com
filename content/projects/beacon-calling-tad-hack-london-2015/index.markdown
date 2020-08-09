---
author: sammachin
date: 2015-05-05 13:25:04+00:00
draft: false
title: Beacon Calling - TAD Hack London 2015
type: page
url: /hacks-and-projects/beacon-calling-tad-hack-london-2015/
---

I attended my first TAD Hack event back in April, TAD Hack is a hackday aimed at telecom application developers, so in general its going to be people that like playing with things like SIP and WebRTC, possibly dabbling in a little light SMS!

Although the driving theme of the event was WebRTC as thats certainly the hot topic in comms hacking right now I was interested in seeing what TruPhone had to offer, I've long taken an interest in TruPhone as they're a proper telco with HLR's and core infrastructure but they act in a far more hacker friendly disruptive way, just because there isn't a standard and a vendor offering a solution doesn't stop them from doing it. They push the industry forward.
One of TruPhones assets is they have large pools of numbers and they'd brought along a new API that would allow me to point those numbers at SIP endpoints and switch them around in real time. The other technology I'm very into is iBeacons, partly because they're another hot topic and partly because I want to show that there are many uses for them which doesn't involve spamming users with adds in some kind of Minority Report inspired dystopian nightmare!

So how to combine the two into a simple but useful and valuable hack.... Enter Beacon Calling.

Many years ago in the days before ubiquitous mobiles we called places, usually we wanted to speak to a specific person but we had to guess which place that person would be at then call there and see if they were. Back in the 90's Orange even made it part of their 'vision of the Wirefree future' that you would call people not places. In general that whole part of telecoms has worked out pretty well, most of the time this is what we want to do. However sometimes you need to calla place, and speak to someone, anyone thats in that place. The most common one for most people is probabbly calling the office, you've left something behind or need to check up on something and you need someone in the office that can do that for you. But in a world where everyone has a personal mobile thats not so easy, so you end up back in the scenario of phoning around multiple people asking "are you in the office" We've come a full 180 degreess in less than 20 years!

So how did I build the hack, well the idea is pretty simple. Attach a TruPhone number to an iBeacon then that iBeacon gets placed in a physical space. Now iBeacons are pretty dumb devices, they're certainly not capable of handling a voice call. What the iBeacon does is broadcast an identity every 500ms or so. My hack consisted of 2 main components, an iPhone app that would monitor for the beacons and then when it came into range of one it would post the beacon ID along with the users device ID to a central server. This server would then have a list of all the users that were in the vicinity of the beacon. The TruPhone number was then pointed at a bit of simple middleware code running on Twilio to take incoming calls and fetch the list of users that were near the beacon, the call was then forwarded to all the users devices running the TruPhone app as a SIP call. Boom! instant location specific hunt groups.

In a fully commercialised version of the application there wouldn't be any need for the separate app that functionality could be built into the TruPhone VoIP app, the huntgroup part could be done with any kind of commercial SIP Application server, twilio was just a quick way to test, hopefully this functionality will be part of a upcoming TruPhone API. You would probably want some kind of web based administration of beacons to control who could actually join the group, after all you probably wouldn't want a customer walking into your business and suddenly their phone has become part of your hunt group! But so far as a Proof Of Concept built in a single day I think its pretty successful. Thankfully TruPhone thought so two and I won the TruPhone prize, thanks again guys.

There's a video of me demoing the hack embedded below. I havn't posted the code as its all a bit of a mess but if you're interested in any part of it get in touch.

<iframe width="560" allowfullscreen="None" src="https://www.youtube.com/embed/e4toIPXHVpY" frameborder="0" height="315"></iframe>
