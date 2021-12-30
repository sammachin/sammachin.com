---
author: sammachin
date: 2014-09-12 12:37:05+00:00
draft: false
title: Indie Talk
type: page
url: /indie-talk/
---

For quite a while now I've been thinking, talking and hacking away on something I'm calling The Talk Project, I won't go into too much detail about that here, you can read some more on the sites own page, and I'm intending to add a lot more to that site in the coming months.

[The Talk Project](http://talkproject.org) has a lot in common with the [Indie Tech ](http://ind.ie/manifesto)movement and the [IndieWeb](http://indiewebcamp.com) scene, whilst it might not be 100% aligned with those aims I certainly relate to a lot of what they are about therefore I'm really happy to announce the first release under  the Talk Project uses some of the technologies that have been developed by the indieweb community.

Introducing [IndieTalk](https://github.com/sammachin/IndieTalk_FrontEnd), the concept is that you can drop some HTML/CSS/JS code onto your website which allows you to login and people to talk to you all using Indie Auth, right now this is what I'm tentatively calling a Level 1 release, that is that the front end code lives on your server and you are identified by your own domain but the back end application logic and services to enable the real time comms are hosted, in this case they are hosted and run by me on a small virtual server from OVH, It also uses the public [STUN](http://en.wikipedia.org/wiki/STUN) server run by google for the time being.

I'm intending to release more of the back end stuff in the next few weeks once its packaged up, therefore you should be able to replace my infrastructure with your own.

If you'd like to give it a try then grab the code from [GitHub](https://github.com/sammachin/IndieTalk_FrontEnd)  you should be able to just drop it into a folder on your site (I'm using /talk) then visit your site at http://example.com/talk, login with IndieAuth and away you go!

This is very much an early beta release for people to experiment with, please let me know of bugs and issues, Github is probably the best place to raise those, I make no commitments about the availability of the back end server although I'll try not to break it until at least I've released a version you can run yourself, also things like security hardening and SSL are still to come so I wouldn't recommend this for those top secret and important communications.

Below is a short demo video of things in action, I've tested this on Chrome, Firefox and Opera on my Mac as well as Chrome and Firefox on Android, it doesn't work on any iOS browser at the moment as there's no WebRTC support in iOS, thats a whole world of work I need to think about a lot more.

<iframe src="//www.youtube.com/embed/9cUgyVqLMko?rel=0" allowfullscreen="allowfullscreen" height="315" frameborder="0" width="560"></iframe>

I'd also like to just call out a few people who've helped build things that have enabled this; I'm using [Tim Pantons](http://babyis60.wordpress.com/) fork of the Open Source [Phono ](http://phono.com/)libraries, to talk to [Prosody](http://prosody.im/) as the BOSH/XMPP server. The UI is built with the [FireFox OS Building Blocks](http://buildingfirefoxos.com/) and of course [Aaron Parecki](http://aaronparecki.com/) for the [IndieAuth](https://indieauth.com/) piece. The backend web app was built by me in Python using the Tornado framework.
