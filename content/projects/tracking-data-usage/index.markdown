---
author: sammachin
date: 2014-07-14 13:11:58+00:00
draft: false
title: Tracking Data Usage
type: page
url: /hacks-and-projects/tracking-data-usage/
---

A few months back I changed ISP over to[ Andrews and Arnold](http://aaisp.net/), they're great by the way, not the cheapest but I'm a big believer in you get what you pay for and they certainly delivery a quality product.

One of the things about the new account was I now had a fixed quota of usage (100GB per month) my previous ISP gave me 50GB for peak usage and unmetered off peak, I knew I never went over the 50GB peak but I had no idea how much I used in the evenings, particularly as that was the time when I'd use the heavier services like watching Netflix.

I needed a way to visualised my usage and also to try and stay on track so I didn't run out of quota before the end of the month then have to buy more, equally I wanted to make sure that I was making the most effective use of my allowance and not leaving masses to spare whilst restricting my usage. I've long been a fan of the [burndown chart](http://en.wikipedia.org/wiki/Burn_down_chart) for tracking the work to do on a project, I had a thought that this could also be a good way to monitor my quota usage, effectively I start each month with 100GB and the target is to get to 0 at the end of the month, not too soon so I run out but not leaving any 'unspent' data either.

At the time A&A didn't have an API to get my current usage in a nice clean programatic way but they do have some pretty simple web pages showing the use that I could scrape, since I first wrote this they've now launched a beta version of their API to get usage and I've updated the code to use that. The application is pretty simple, its written in python and uses CherryPy to expose a couple of web functions, one is an /update method which calls A&A with my login details to get the current usage for the month, this then stores the value against the date in a pickle file. The other function is the display which loads the data points for each day of the current month from the pickle and then plots that on a google chart, there's another function which is called at the beginning of each month to create a new pickle file and plot the target use for the month onto the chart. The update and new month functions are called from a cron job with the update being run several times a day. I can then easily glance at the graph to see how my current usage is doing, if I'm too far below the line then I'm getting ahead and I need to try and ease off any major downloads, if I'm well above the line then I have qutota to spare and I can stream video till my hearts content.

I've published the code on [GitHub](https://github.com/sammachin/databurndown) if you're with A&A please feel free to make use of it, I run the whole thing on a raspberry pi at home but it would run on pretty much any server that you can install python onto.

[![burndown_june2014](http://sammachin.com/wp-content/uploads/2014/07/burndown_june2014-300x252.png)
](http://sammachin.com/wp-content/uploads/2014/07/burndown_june2014.png)

As you can see for the June graph I started the month using quite a lot of data then levelled off then hardly used any for about 5 days (we went on holiday to NYC) and ended the month with around 30GB to spare.

Personally I really like this way of understanding my usage, I wish more service providers would show it in this way, although most of them have a [financial advantage for you not to use your whole quota](http://en.wikipedia.org/wiki/Breakage)
