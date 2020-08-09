---
author: sammachin
date: 2014-08-26 10:58:10+00:00
draft: false
title: A platform based bank account
type: post
url: /blog/a-platform-based-bank-account/
categories:
- Blog
---

For a long time I've always felt that telecoms and banking/payments are pretty similar industries when it comes to technology, both handle massive amounts of real time transactional data, making a payment in a shop using a visa card is fairly similar to the idea of sending someone an SMS when you strip it back, of course payments have to have higher levels of security than telecoms but we're in the same ballpark. I've had an idea at the back of my mind for a few months that I call the Platform Bank Account. Looking at the success of [Twilio](http://twilio.com) (and other telecoms API platforms) I started thinking what would a 'Twilio for banks' look like.

First things first I need to get a few things clear, it might be easier to say what this isn't; I'm not talking about an integration between  Twilio and my bank so I can get SMS alerts of my balance or when I go overdrawn, neither is it a way to take payments or send friends money along the lines of [PayPal](http://paypal.com) that then sits on top of a 'real bank account' or [Stripe](http://stripe.com). What I am talking about here is a first class, real bank account, with a sort code, account number and everything, to any other part of the banking system it looks like just another current account and has all the same capabilities. What makes this account different is that its a platform, exposed by an API so that any myriad of 3rd party applications can be used to manage it, both via user interaction and automatically.

Lets look at the main features of most current accounts, I'm not talking about the gimmicks that banks tack on to sweeten the deal like [phone insurance](http://www.lloydsbank.com/current-accounts/added-value-accounts/platinum-account.asp?WT.ac=CCAPFOM1) or a [free gun](http://articles.latimes.com/2001/mar/19/business/fi-39732)! just the things that are the real reason for having an account;

_Account Number and Sort Code_ - This is the primary identifier for your account, its used so that your account can function in the system with other accounts, it also has global versions like the IBAN, obviously our account will have one of these.

_Direct Deposit_ - Most people get paid their salary or whatever by direct deposit into their account, this is why your account needs a number (see above)

_Direct Debits_ - If you want to be a grown up you'll  have to pay bills, generally by DD. Council Tax, Utilities, Mobile Phones all of these need the ability to make DD requests to your account number.

_Standing Orders_ - Like a direct debit but these allow money to be 'pushed' from your account to another on a schedule you define.

_A Debit/Cash Card_ - Probably the main way people interact with their bank account on a daily basis this is 2 or 3 things in one, it allows you to get cash out of an ATM, Make Payments in shops using Chip & Pin, contactless etc. and also it has a 16 digit number that you can enter to buy things online. Payments made on this card then show up as a debit on my account (or credit in the case of refunds)

_Faster Payments_ - I can make a one off payment from my account to someone else's account number, usually via some fairly tedious web site.

_Cheque Books_ - Ok most people here probably think these went out with the ark but they're still around and people do use them, they're a feature of most accounts.

_Counter Service_ - I can goto a physical place and either withdraw or pay in an amount of cash or even one of those old fashioned cheques, usually this is my banks 'branch'

_Balance_ - Possibly one of the most obvious and maybe overlooked features is that my account is somewhere I can store 'money' it has a balance and this facilitates most of the payment features above

_Overdrafts_ - I guess this is a feature or maybe its just part of the balance but my bank will also allow me to have a negative balance for a short while, this makes things easier with payments if the timing doesn't quite line up.

I think thats it, above is what makes up in my mind a current account,  many of us will have other things from our banks like loans, mortgages, savings and credit cards but to me these are separate products from the current account.

In my head I've distilled this down to a few key points, An account is  a 'thing' which is identified by a number and allows transactions to flow in and out of it wither by push, pull or scheduled. Well that sounds a bit like telecoms, where you have a 'thing' identified by a phone number that allows calls and texts to be made to or from it? So if we think about  what twilio is for telecoms what is this new platform for a current account;

_Account Numbers_; I need at least one of these, its the primary key. But why should I have only one that has to route everything through it? Why can't I have multiple 'alias' account numbers that I can create or destroy as I need?

_Balance_ -   I'll need an overall balance for the amount of 'money' in this account, but maybe each of my alias numbers above also have a virtual balance, and this virtual balance can be positive or negative, its not real money I can shuffle around these as needed, perhaps I like to have a spending account which I reset to zero at the end of each month. So long as my master balance is positive then it doesn't matter.

_Overdraft_ - Useful feature, and only really applies to my master balance as thats really my money, not everyone will have or want it but its an option.

_Direct Debits_ - Can be setup from any one of my account numbers and work exactly the same way, however I can also attach a 'trigger' to the DD to notify a web service when a payment is requested/made.

_Direct Deposit_ - Again money can be paid to an account number and I can fire a trigger to an application when money is paid in.

_Standing Orders_  - I can setup/modify/cancel a standing order via an API and that S/O can have triggers to notify applications when it is made.

_Faster Payments_ - Like an S/O I can initiate one of these with an API call and applications can be notified.

_Debit Card_ - I have one (or more) physical cards linked to the account and payments made with the card can notify an application, same for ATM withdrawals. I can also generate new 'number only' cards which don't have a physical card for use online, I can choose the expiry date of these numbers and cards from 1month to 5 years.

_Cheques_ - I can generate a cheque to pay someone via the API, this is returned as a PDF which I can then print or send to them electronically. Whenever a cheque is generated or cashed I can configure applications to be notified.

_Counter Service_ - My 'bank' has an agreement with another High St bank or maybe the Post Office so that I can  transact cash or cheques in the real world, these events also result in a notification to my applications.

So thats about it, not really very different from a standard account, all the same features are there, the major difference being that the the transactions you would normally only do via the banks internet banking website are available via an API and when actions hit your account such as debits or credits you can configure a 3rd party service to be notified. This in turn would allow services to be built that can link these. For example I might have an app that says 'When my expenses get paid in initiate a faster payment to my credit card then send me an email.' Or I might want to create a separate visa card number to use for iTunes which sends me a push notification whenever a transaction is made. The idea is that these are building blocks we can integrate into the applications and services of our daily lives, I don't know all the ways that people would want to use and manage their accounts and I'm sure that their bank doesn't either.

Its worth talking for a moment about security as well, I expect most traditional banking people are screaming at this idea right now as being far too dangerous and who would ever grant a 3rd party access to your account, yet this is exactly how direct debits work, and with a realtime notification system as well as the ability to revoke actions the risk should be greatly reduced. In terms of granting applications permission I envisage some sort of oAuth type of process with permissions and limits, so when setting up the expense example above I might grant _AcmeExpenseManager_ permission to receive notifications when a payment is made from "Company X' and permission to initiate a payment to 'Credit Card Company Y' with a monthly transaction limit of say £500, this would be like giving a Facebook app permission to post to your wall, you'd still see a permissions screen from your bank, be asked to enter a password (with 2 factor auth) to agree to it and have the ability to cancel/revoke the permission from the banks site  at any time.

Notifications would be similarly configured so that an application would ask for permission to be notified of transactions meeting a certain set of criteria, e.g. whenever a Direct Debit is taken from my account of between £10 and £100 pounds, notifications would contain the full details of the transaction e.g. account number, reference,  sender/recipient, date/time, amount and optionally balance of the account. You could configure multiple notifications for the same type of transaction.

Whats the business model here? well for the bank its pretty much the same as any regular current account, except the 'added value' is in terms of the plan your on rather than gimmicky free gifts. Lets say the basic account gives me 1 physical card, 5 virtual cards and 3 account numbers,  I can configure 20 different application notifications and all of this is free, the rest of the usual type of add-ons apply If I use the card internationally I pa a couple of percent commission, if I choose to have and use an overdraft I pay a monthly fee, the interest on my credit balance is pretty poor and if I'm overdrawn again I pay a higher rate of interest on that balance, the bank makes money in exactly the same way. Or I can choose to upgrade to a higher plan called  Silver/Gold/Platinum etc. these will add the ability to have more physical & virtual cards, more account numbers and more notifications maybe I also get a better deal on international transactions and a fee free overdraft, for these tiers I pay a monthly fee of between £5 and £20 just like todays' High Street accounts.

This isn't about radically changing the core of banking its about exposing that core service to the digital world, I'm happy to pay for the service and I don't really have a problem with the way bank accounts work, what sucks is the front ends I have to access them, I want to link my account to the rest of my life, using services like [IFTTT](http://ifttt.com), [Expensify](http://expensify.com), Google Docs and even FourSquare!,  with push notifications and all in as near to realtime as the systems will allow.

So tell me this can't be done? Fine I know this is a grand design, but if there is something thats stopping it, then lets fix that clear the barriers and at least try, don't just sit there and say NO. I'm sure this will need some established mainstream bank that has access to the back end network to at least sponsor it if not implement it, and I don't expect they'd launch this on their main brand, but there must be the MVNO equivalent for banking?

I'm not 'announcing' this, nor is it something I'm even building its just an idea in my head, and I'm sharing it with the world because I'd much rather someone else made it happen than it just sat locked up in my head, but if you're reading this and think you've got whats needed to do it then get in touch and lets talk,  I'd love to work on it but I can't do it on my own.








