---
author: sammachin
date: 2015-05-05 20:10:50+00:00
draft: false
title: SMS Lists via Google Docs & Twilio
type: post
url: /posts/sms-lists-via-google-docs-twilio/
---

Let face it the world runs on spreadsheets. Although meant as a financial tool they've found their way into just about every part of a business and quite a few home uses too. Databases, lists, forms, even data manipulation for things like logfiles end up being done in spreadsheets. Why? because they're a tool everybody has, any anyone can use. Whilst as developers we like the idea that businesses will use beautiful web-apps with fancy noSQL backends and running the latest hipster frameworks the truth of the matter is that day to day most stuff happens in excel, and if people need to share that stuff they email the file around.

Google Docs is a pretty good balance, its kept the familiar interface and basic functionality that most people like in excel but then its brought things into the web age, we can now collaborate on a spreadsheet without firing emails back and forth or worrying about versions getting out of sync.

Therefore I thought that Google Docs would make a pretty good backend for a small business tool, in this case group text messaging, again as devs we love Twilio for its clean API and multitude of supported languages but most people just want a way to send a text to a bunch of people and they can't write code. This is where SMS List Sheet comes in. I've built a simple app running on heroku that sits in between Twilio and Google Docs, allowing users to create multiple SMS group lists and adminstrate them without needing to write their own code. 
The idea is that a user can setup their own Twilio account with their own credit and then buy numbers whereever they like, they then point those numbers at SMS List Sheet and on the other side they create Google Spreadsheets that are shared with the app, then my code just bridges the gap. Its fully multi-tennanted and all your data remains inside your own Google Docs accounts, the app itself is stateless and stores no user credentials.

A quick note about security, as far as I can tell this app will keep your data private, you need to share the google docs with my app but other users of the app have no access to your sheet, in addition you need to put your Twilio credentials into your sheet, my app will then read those whenever it receives a message. Obviously this means trusting me and my application with your Twilio credentials, although I won't be able to see your spreadsheets in my Google Drive I could in theory access them via the API just as the app does, If you're not comfortable with that then setup a separate Twilio account just for this app or wait a few days and I'll post the code onto GitHub along with how to setup your own instance.

Checkout the demo video below or if you want to give it a try yourself then goto [https://smslistsheet.herokuapp.com ](https://smslistsheet.herokuapp.com)

<iframe width="560" allowfullscreen="None" src="https://www.youtube.com/embed/FGTZEdLs3Bk" frameborder="0" height="315"></iframe>
