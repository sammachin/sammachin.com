---
author: sammachin
date: 2009-07-01 15:31:41+00:00
draft: false
title: iPhone 3.0 MMS Settings
type: post
url: /posts/iphone-30-mms-settings/
---

I've been experimenting with my unlocked 3.0 iPhone 3G for a week or so now and I've just got the MMS Settings sorted. see below for details and an explanation of what you need

<!-- more -->

The settings can be found in:

Settings -> General -> Network -> Cellular Data Network

You should have 6 fields for MMS

**APN** Some operators will use a separate apn for MMS some will use the same as the browsing one, Orange UK have a separate one named _orangemms_ so enter that here

**Username & Password** again some this varies by operator, some require a generic username and password, some need any values and some networks you can leave it blank, for Orange UK you can leave it blank.

**MMSC** This is the url that your phone POST's the messages to, if this isn't correct you won't be able to send but you can probably still receive messages. for Orange UK it should be _http://mms.orange.co.uk/_

**MMS Proxy** When you phone sends or receives data from the MMSC it needs to send these connections through a proxy typically this is a WAP Gateway and it adds important information to the requests to identify your handset, like the phone number. It will consist of an IP address and port, the iPhone uses WAP 2.0 as its standard so the port number will usually be 8080 (you may see 9201 used which is for WAP 1.x which is a VERY old binary protocol) again for Orange UK this should read_ 192.168.224.10:8080_

**MMS Max Message Size **This gave me quite  a headache, the MMS standards specify a max MMS size, the 3 steps are 30k, 100k and 300k . Most networks these days support 300k. I've seen a number of sites quoting this value to be 3072, however when using this I found that I could only send MMS's containing text, an images would fail. Following some extensive testing I found that this value is in Bytes, therefore 3072 would be 3k! Pretty small for an MMS, I've set mine to 307200 for Orange UK which is 300k assuming that 1k is 1024 bytes, this works fine. Interestingly the iPhone also rejects any messages sent TO it which are over this size, this differs from most handsets

**MMS UA Prof URL** This is used for one of the headers whcih tells the MMSC where to find an XML file containing the devices' capabilities. It can safely be left blank for Orange UK

[caption id="" align="alignleft" width="320" caption="iPhone 3.0 Orange UK MMS Settings"][![iPhone 3.0 Orange UK MMS Settings](http://farm3.static.flickr.com/2540/3678841446_b28789895a_o_d.jpg)
](http://www.flickr.com/photos/sammachin/3678841446/)[/caption] 
