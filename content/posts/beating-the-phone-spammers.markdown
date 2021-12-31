---
author: sammachin
date: 2014-07-14 14:21:51+00:00
draft: false
title: Beating the Phone Spammers
type: post
url: /posts/beating-the-phone-spammers/
---



[![2995004692_40f34aa78d_b](http://sammachin.com/wp-content/uploads/2014/07/2995004692_40f34aa78d_b.jpg)
](http://sammachin.com/wp-content/uploads/2014/07/2995004692_40f34aa78d_b.jpg)

Ever since we moved into our house over 7 years ago now we've had a real problem with phone spam on the home number, we took over the same number as the lady who lived here previously as it was the fastest way to get a connection so that I could order ADSL on the line, I think I got it to 4-5days after we moved in :)

However the lady that lived here previously obviously liked to sign up for every bit of junk mail going and in turn seemed to give out her home number without a care in the world, she was older and lived alone so I'm guessing maybe she liked getting these sales calls. However I am not so fond of being sold to in any way i i want something I'll go and find it out for myself, and I certainly don't appreciate being called at home when I'm trying to work|sleep|eat or generally enjoy the sanctity of my own home.  Now we've done all the usual stuff like registering for TPS but that clearly is about as much use as a chocolate fireguard and most of these callers were either international spammers who take not notice of our regulations or they were people that the previous owner of the number had 'done business with' probably entering their free prize drawer to win a hald opened packet of polos or something. Therefore the calls kept coming, I'd say we were averaging around 8-10 calls per week at various times, I work from home a lot so they were interrupting me and worse still my wife works shifts and would often be asleep during the day so they'd wake her up. Changing the number wasn't really an idea option as several of our older relatives had the number and bigger still it would have meant disrupting the broadband connection! Besides why should  these bastards cause me inconvenience?

I finally found the solution after geeking up our home phone system a bit, I converted the home system to VoIP using [asterisk](http://www.asterisk.org) [running on a raspberry Pi](http://www.raspberry-asterisk.org/), and an old [SPA3000](http://www.voip-info.org/wiki/view/Sipura+3000) adaptor which converts the old incoming PSTN line into SIP. Our home [DECT phones](http://www.gigaset.com/en_HQ/shop/gigaset-a510-ip.html) already had built in SIP functionality so I could easily connect those to the asterisk box.

Now comes the clever but fairly simple part, when you call our home number the call is now answered by asterisk initially, if the caller ID is on our whitelist of friends & family then it simply connects on to ring the DECT phones, (along with a soft phone on my mac and a few other convenient endpoints) However if you are not on the whitelist or it is an unknown/witheld number then a simple [announcement](http://sammachin.com/?p=188) is played asking the user to press 1 to confirm they are a real person. If they do this then the call is connected onto the handsets as if you were known, if they don't then after a time the call is dropped and we are not inconvenienced. All the incoming calls are logged so I can check for false positives and I even send a silent push notification to my mobile using pushover so I can glance and see that someone is calling (and usually getting defeated by the system)

We've had this running now for about 6 months, and frankly I'm amazed at how well its working, I generally thought that some of the cold callers would hit 1 and connect on, however we havn't had a single one get through the net, what more impressive is that (as far as I can tell) we've had no false positives, using the callerID our family are getting through without noticing any difference and we've had a few businesses legitimately call us that have negotiated the hurdle without issue, I even asked at the local vets who called with some test results if they'd found it odd being asked to press 1 and the girl said she hadn't even noticed it. We are so accustomed to having to press options when calling a company these days that is clearly second nature.

Now the interesting question is why is this so effective at defeating the spammers, well I suspect much of it has to do with the way they make their calls, legitimate callers will dial you number on their keypad when then want to call you, and as such they they have said keypad available to press 1, however the spammers are often making the calls through an automated system that dials the numbers on a list and then connects the calls to an operator once answered who then has to try and sell you the crap. This means that the operator usually has no keypad and even if they get connected to my announcement they can't press 1.

In effect what we have here is the equivalent of a [CAPTCHA](http://en.wikipedia.org/wiki/CAPTCHA) for phone calls, I'm not sure how best to share/publish the code for this as there's isn't very much to each piece just the way I've put it together, if you want some help implementing it for yourself though then feel free to ask questions, best route is probably twitter see the links in the footer.



(image credit [https://www.flickr.com/photos/theshadowknows/2995004692](https://www.flickr.com/photos/theshadowknows/2995004692))
