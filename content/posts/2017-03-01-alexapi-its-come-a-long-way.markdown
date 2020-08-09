---
author: sammachin
date: 2017-03-01 22:27:20+00:00
draft: false
title: AlexaPi - Its come a long way
type: post
url: /blog/alexapi-its-come-a-long-way/
categories:
- Blog
tags:
- alexapi
- github
- open source
- raspberrypi
---

![](http://sammachin.com/wp-content/uploads/2017/03/IMG_4774-300x225.jpg)

Its over a year now since I released the first version of my AlexaPi code that turned a Raspberry Pi into your own Amazon Echo like device via the Alexa Voice Service API.
When I say released thats a bit grander than it really was, at the time I'd hacked this thing together and thought I should probably put the code up on GitHub as it might be interesting for others. 
My code is bad, really bad. I've always said I'm not a professional developer, I come from a background of sysadmin, and these days I'm more of a systems architect. But I can hack together some interesting things. 

I never expected the project to gain any traction, mot of the stuff I've done might have had a small handful of people take it and adapt to their own needs but AlexaPi seemed to really hit a note with people and is still going strong, as of today the 1st of March the original repo has been starred 673 times and forked by over 400 people. Its hard to know what that means in terms of actual installs, I suspect most people just download or clone the repo and flash their own Pi, I never put any tracking into this and there is no backend that I control so I can't see any real usage stats but I would estimate the users to be in the thousands.
Even in the last month the repo has been cloned nearly 100 times and the project has had 1300 unique visitors, so its still going strong.

Which is why it might seem a little strange that today I changed the name of the repo to AlexaPiDEPRECATED, and moved it out of my github account, Its not dead just that today marks a significant milestone.
As I mentioned earlier there are many forks of my code, and this meant that people were modifying it for their use and extending the functionality, this is the great thing about open source and I love seeing people build stuff on top of what I started, however it also meant that things we're getting a bit out of control, people were asking questions, raising issues and sending me pull requests that I just didn't have time to manage, (its also a year today since I went back to a full time salaried job which has taken up a large portion of my hacking time.)

Sometime last year (I can't find the date) a guy named Rene Kliment contacted me via the project, he wanted to start work on consolidating the forks into a single great AlexaPi project with cleaner code, support for different hardware platforms and a generally more modular approach which should facilitate people sharing their own custom integrations without having to fork the codebase. 
I'm still amazed at the work he's put in, and this is the really boring grunt work of cleaning up someone else's code, rather than adding fancy new features that do cool things for You Tube videos, I would never have had the time, skills or patience for that!

So today the Rene as the 'Chief Steward' of the Alexa-Pi project released v1.4 of the code, this now puts the project on par in terms of features with my original version along with some of the improvements added by other contributors, the code is cleaner and a lot more professional, things that I hard coded for my particular setup are now more flexible and generally everything is a whole lot more awesome. 

I just want to say a huge thank-you to Rene, and all the other people that have contributed to the project, a few of the name that I know of  are Mason Stone, Travis Teague, Lenny Shirley, Aleksey Maksimov, Mark Jozefiak Dion Gonano, I know there are many more out there that have contributed to the project and you will be immortalised in the commit history, thank you everyone. 
I'm intending to get more involved in the project this year, I've submitted a couple of contributions this last weekend and been doing a bit of testing behind the scenes, hopefully I can provide support and advice to the developers and users along with generally cheerleading their work. I was lucky enough to be named by Amazon as an Alexa Community Champion partly because of this project so I need to keep championing the community.

If you haven't checked out the project then now is a great time, everything is centred around the Repo at [https://github.com/alexa-pi/alexapi](https://github.com/alexa-pi/alexapi)

