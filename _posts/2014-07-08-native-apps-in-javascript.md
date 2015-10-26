---
title: Native Apps in JavaScript
author: Tim Tutt
layout: post
permalink: /2014/07/08/native-apps-in-javascript/
tumblr_post_id:
  - 91120797066
idptt_tweeted:
  - 1
categories:
  - Application Development
  - Databases
  - MongoDB
  - Programming
  - Software Development
tags:
  - Andrioid
  - Appcelerator
  - iOS
  - JavaScript
  - MongoDB
  - NoSQL
  - Parse
  - Titanium
---

Who would have thought that writing a native mobile app entirely in Javascript was possible? I know I was a skeptic initially. Yet &#8211; the first [mobile app][1] I wrote was written **entirely** in Javascript &#8211; and you&#8217;d never know it if I hadn&#8217;t told you. How did I achieve such a feat? Sadly it wasn&#8217;t anything as exciting as black magic. I used two very powerful frameworks to churn out an awesome app: [Appcelerator&#8217;s Titanium][2] and [Facebook&#8217;s Parse][3] Frameworks.

**On Titanium**

  *  Why Titanium? &#8211; I wanted the flexibility to make a cross-platform app*
  * I knew JavaScript (or so I thought)
  * Appcelerator seemed to have a stable enough platform and powerful enough SDK*
  * **Free** platform and did not require me to send my code elsewhere to get compiled
  * There were plenty of modules out there for me to use for random things.

That said &#8211; let me say three things:

&#8220;Cross-platform&#8221; frameworks don&#8217;t mean 100% cross-platform. What this typically means is you will be able to share 80% of your code (business logic and some UI stuff), but you still have to write specific things for each platform. I realized this about half way through my development effort and because I&#8217;m an Apple user myself I chose to go the iOS route. About half way through my development, iOS 7 was release with all the lovely UI changes and I had to completely scrap my UI and re-write it (worked out for the best, I like the current design). Note &#8211; this is all in JavaScript &#8211; You basically create JavaScript objects that have the same properties iOS UI Elements do.

The second note is &#8211; I thought I knew JavaScript before I embarked on this task. I realized that I in-fact did not know it as well as I thought I did. Handling memory is very different from how you handle memory in other languages, and there are other random nuances about polluting namespaces and such. This is a self-correcting problem if you can identify what problems you&#8217;re actually experiencing (memory leaks and the like).

Finally &#8211; There are a number of Titanium modules out there for you to throw in to your code. Plenty of them are free and open source. These modules are written in the native languages (Objective-C/Java for iOS and Android respectively) and are exposed to you via a JavaScript API. There were a few times I had to get my hands dirty and actually dig into some Objective-C code to modify these modules to do some additional things I needed, but that wasn&#8217;t too terrible, and the Titanium Framework makes it pretty easy to re-deploy.

**On Parse**

  * Parse was attractive because of the pricing model*
  * It is MongoDB on the backend so it is scalable.
  * Cloud Code* is amazing.
  * More JavaScript

Parse&#8217;s pricing model when I started was a freemium model that was based on the # of queries. This is great for scaling up. You&#8217;d pay nothing for the first 1,000,000 queries a month. After that the pricing did take a bit of a jump, but it was manageable. My thought was &#8211; if I&#8217;m hitting 1M+ queries a month, I&#8217;m probably making money. This did, however, put a bit of a damper on some things I wanted to do at first. I wanted to track all kinds of metrics and had to be creative about how I collected information and sent that back to the server. It wasn&#8217;t elegant, but it got me my data. Then something wonderful happened &#8211; At F8 (about two weeks before my launch), Facebook announced a new pricing model for Parse. No longer were you bound by the #of queries, but now by the #of queries per second (with some room for bursts). I re-wrote a lot of my business logic that very night and track everything. (Thanks Zuckerberg).

Parse also has this nifty little thing called Cloud Code. It allows you to write JavaScript functions that run on the server so you can actually offload a lot of your business logic from your app to these Cloud Functions. Additionally, you can create cloud jobs that can run on your data in a scheduled manner.

On launch day &#8211; Cloud Code saved my life. I was obsessing as any developer would when their product hits production and kept checking to see how many downloads I was getting/users. The first 4 of the first 10 users to sign up all had some missing data (I was checking it through Parse&#8217;s data browser) that my app was supposed to be providing in order for them to actually use it. Long story short &#8211; I had an edge case that I hadn&#8217;t accounted for, which was actually a bigger edge case than I assumed. Luckily &#8211; I was able to update my cloud code logic such that on save it checked for these errors and appropriately handled them so the users never knew there was an issue and I didn&#8217;t lose them because of a stupid bug that I was able to fix with one safety check.

**Other Thoughts**

Writing an app entirely in JavaScript isn&#8217;t all pluses. The Titanium Developer community is not one of the most active communities. There were many cases where I spent hours looking at forums for ways to solve odd problems I was having. In most cases I had to hack away to find the correct solution. Appcelerator certainly tries to keep Developers active so it&#8217;s hard to say why that is. I should also note that Titanium also has a cloud storage backend. I honestly don&#8217;t know much about it and had trouble finding many others using it (likely because it was early on in the life cycle). It may be a completely viable option, but I can&#8217;t comment on it. I can&#8217;t say I&#8217;ll use Titanium for my next app simply because of the lack of activity in the developer community (certain functionalities in iOS won&#8217;t be easily usable without modules being built). Luckily I won&#8217;t have to learn Objective-C and Swift is pretty damn close to JavaScript.

Parse &#8211; has completely won me over. Ease of use. Great documentation and the developer community is extremely active. Will likely be using Parse for future mobile apps, web apps, etc&#8230; Would recommend it to just about anyone. They have had their stability issues &#8211; this happens when you have a scalable platform with many users, but they are very quick about fixing them. Downtime has been minimal in the last 60 days.

Moral of this story: Mobile Apps can be written entirely in JavaScript and still feel native. [Writer&#8217;s Block][1] is proof.


 [1]: http://www.writersblockappios.com
 [2]: http://www.appcelerator.com/
 [3]: https://parse.com/
