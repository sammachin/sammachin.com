---
author: sammachin
date: 2021-12-30 11:50:43+00:00
draft: false
title: AlexaWeb Reborn
type: post
url: /posts/alexaweb-reborn/
tags:
- alexa
- node-red
- avs
---


6 Years ago this month  I published one of my first Alexa hacks, [Alexa In The Browser](http://localhost:1313/posts/alexa-in-the-browser/) This was one of the key projects that got me into Alexa Development and lead to me being nominated as one of the first Alexa Champions.

I have to admit to neglecting Alexa stuff in the last couple of years, however the alexaweb app has been happily running on Heroku serving users for all that time with zero attention from me. Its never been hugely popular, which fortunatly has also kept it within the confines of the free tier, but it was getting traffic every day. Looking at some stats on the Amazon auth settings it's had over 21,000 unique alexa users login to it.

All was good until a few months ago when I had a message from someone saying that it was no longer working, I didn't have much time to dig into things at that point so I had to mostly just apologise and say I'd look at it when I could but its very old. 

Over the holidays I finally had some time to look into things, until now all of my alexa voice projects have been using the v1 api, it was a fairly simple REST-like interface, you posted an audio file to the API and it sent back the response as another audio file. In early 2016 Amazon released an updated version of the Alexa Voice Service known as `v20160207` (going for the date of release as the version number) This was a very different API, the major thing was that it used HTTP/2 and held open a persistent connection.
I did look into updating my projects to use this API but back i n 2016 HTTP/2 was pretty new and none of the client libraries were very mature. At the time I thought it was a mistake to be requiring such a new protocol for an API. 

When I started to look into the failures with my alexaweb app it became apparent that the responses from Amazon were not the audio that I was expecting, I was getting back an HTML page with a rather generic error. This had been going on since the end of October 2020 so I think its fairly safe to say that Amazon have shutdown the Alexa Voice Service v1 API, although I've not been able to find any notices about deprecation.

This kind of forced my hand into getting my head around the v20160207 API, fortunatly HTTP/2 support has improved a lot in the last few years, I also decided to port the app over to Node as I'm not really writing much Python these days. Node has native support for HTTP/2, with a bit of googling I found some sample code where others have been trying to talk consume the same API with varying sucesss.

I've been working in Node-RED with a function node mostly for the rapid iteration that gave me trying to figure out the API call and the formats that were returned, it allowed me to inject the same request audio again and again without having to keep saying "Alexa what time is it" and build other parts into the chain like ffmpeg to manipulate the request and response audio into formats that I could work with in the browser.

After several days of hacking I finally had a working flow that could submit audio to AVS and return the response object in such a way that I could then process it and play out the various audio parts. A few more Node-RED flows to handle the oAuth and serve up the various web based elements and I have a complete rewrite of AlexaWeb under Node-RED!

{{< figure src="/images/AlexaWebFlow.png" >}}

I'm particularly pleased that I managed to implement the whole application using just the core nodes, even if there is a fair amount of custom code in function nodes. I'm not going to publish this flow as is but I think there is value in turning some of the function nodes into a set of custome Nodes for the Alexa Voice Serivce which can then be used to create your own alexa client applications, things like smart home or automated testing could be interesting use cases.

AlexaWeb is now running on an EC2 machine and avaible to try at [https://alexa.sammachin.com](https://alexa.sammachin.com)

{{< youtube DMPfn_SU8o8 >}}

