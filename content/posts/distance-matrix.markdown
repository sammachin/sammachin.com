---
author: nav9ok
date: 2014-07-13 21:51:29+00:00
draft: false
title: Distance Matrix
type: posts
url: /distance-matrix/
---

A few months back there was a serious possibility that we were going to have to move house as a result of my wifes' job, she's an A&E Doctor and I won't bore you with the details but the way that medical recrutment works is its all done on regions and you get allocated/offered a job in a certain region, this will then usually consist of 'rotating' around 5-6 (or more) hospitals every 6-12 months. These hospitals are pretty spread out for example in our current Region she could end up working anywhere from Yeovil to Gloucester to Swindon. This means you either try and live somewhere central to them all and accept a long commute or move home every 6-12 months. When you get to your early 30's though you want to try and settle down and live in one place, or at least thats what we do.

So there we were having to consider a major move to another region, we didn't really know much about a lot of the areas and all we really had was a list of the hospitals but from that we had to try and find where we might want to live, that was A) not a total craphole, B) Affordable and C) within a reasonable travel time of all the hospitals. Initially C was generally consisting of mutiple cut & pastes into Google Maps and trying to work out multiple times.

This was one part that knew could be automated to be much easier, Google Maps have a nice little API called the [distance matrix](https://www.google.co.uk/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&ved=0CCAQFjAA&url=https%3A%2F%2Fdevelopers.google.com%2Fmaps%2Fdocumentation%2Fdistancematrix&ei=3f7CU4LXC9Ty7AaRzoD4Bw&usg=AFQjCNG4uG--V0sCVmx4nca-Nb1afWIvfg&sig2=D62zMHAATmlAiYNb8aUqEw&bvm=bv.70810081,d.ZWU), whereby you can pass in a list of locations alone with a start point and it will tell you the time & distance to each one of them, I don't think this functionality is available in the GMaps web frontend which is a shame as its a really useful feature, anyway I set about building a simple front end to use the API,

The result is[ matrix.sammachin.com](http://matrix.sammachin.com) a little one page app running on heroku, the idea is that you build a list of locations on the left hand side, these ca be anything from postcodes to "Bristol, UK" (remember to specify the country as google will default to globally) then click around the map and it re-calculates the time & distance to each of those points from where you clicked, it was an interesting little project and got me up using the latest google maps javascript as I'd only done stuff with the very old and depreciated v1 & v2 until now.

Its running on heroku so I'll leave it there, it might be useful to someone and its not costing me anything, however I can't guarantee it will always work if google changes something on the API.

[![matrix_screenshot](http://sammachin.com/wp-content/uploads/2014/07/matrix_screenshot-1024x642.png)
](http://matrix.sammachin.com)


