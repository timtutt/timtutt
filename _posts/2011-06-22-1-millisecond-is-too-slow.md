---
title: 1 Millisecond Is Too Slow
author: Tim Tutt
layout: post
permalink: /2011/06/22/1-millisecond-is-too-slow/
idptt_tweeted:
  - 1
categories:
  - Age of Information
  - Application Development
  - Big Data
  - Data Analysis
  - Large Scale Systems
  - Programming
tags:
  - big data
  - cloud
  - etl
  - scalability
  - scale
  - scaling out
---
<div class="twttr_button">
  <a href="http://twitter.com/share?url=http://www.timtutt.com/2011/06/22/1-millisecond-is-too-slow/&text=1+Millisecond+Is+Too+Slow" target="_blank" title="Click here if you like this article."> <img src="http://www.timtutt.com/wp-content/plugins/twitter-plugin/images/twitt.gif" alt="Twitt" /> </a>
</div>

&#8220;640K ought to be enough for anybody&#8221; &#8211; This quote from the 1980s which may or may not be attributed to Bill Gates is quite laughable quote these days. We live in a world where exabytes of data isn&#8217;t even enough to classify the amount of data we will consume as a world in the next five years. For the more non-technical readers out there a exabyte is roughly equivalent to 9&#215;10^15 a kilobyte. To break it down just a little more, that&#8217;s about 10,000 terabytes of information. 

Twitter has about 100M updates per day. We won&#8217;t even begin to guess how many updates Facebook has. Blogging is a ubiquitous term so there are plenty of those out there. What I&#8217;m getting at is there is a lot of data out there just waiting to be analyzed and analyzing data at these volumes is no trivial task. 

Before I end up in a rant about big data let me get to the point. Analyzing data at those volumes takes time. Let&#8217;s look at Twitter for instance &#8211; 100 million tweets per day. Tweets are relatively small records &#8211; 140 characters plus any additional meta-data about the user and retweets and such. Let&#8217;s say it takes about 1 millisecond to process a single tweet. 1 millisecond 100 million times is 100,000 seconds, which is about 1667 minutes, which is about 27 hours. So at 1 millisecond per record it would take just over a day to process 1 day worth the tweets. My point &#8211; 1 millisecond is too slow.

Enter &#8220;the cloud&#8221;. Cloud is probably one of the most overloaded terms in the technology space today so let me apologize for using it and explain what I mean by the term. I&#8217;m talking about horizontally scaling your architecture in order to process these large volumes of data in parallel.

You have to be smart about how you do this. If you have a web service that can only handle two requests at a time and takes 600ms to process data, scaling out to hundreds or thousands of servers does you no good. The bottle neck still exists at the web service. 

We are no longer living in the days where 1 millisecond is considered fast. We live in a world of instant information. 27 hours to process yesterday&#8217;s data is unacceptable. 

So how do you fix this? You optimize your processing algorithms. This is my call to software engineers everywhere to start optimizing your code and prepare for scaling so that your code meets the demands of today and tomorrow. Eliminate bottlenecks in your code and make those that you cannot remove scale horizontally. Stop accepting &#8220;good enough&#8221;. 

It&#8217;s a tall order coming from a small fish low on the totem pole. There is a completely different mindset that software engineers have to switch to in order to achieve this. You have to stop thinking about solving problems in a single threaded manner and move to thinking about problems in parallel. 

It&#8217;s a new age with new rules. Take the advice or leave it, I&#8217;m just a guy that deals with big data on a daily basis.

<div class="twttr_button">
  <a href="http://twitter.com/share?url=http://www.timtutt.com/2011/06/22/1-millisecond-is-too-slow/&text=1+Millisecond+Is+Too+Slow" target="_blank" title="Click here if you like this article."> <img src="http://www.timtutt.com/wp-content/plugins/twitter-plugin/images/twitt.gif" alt="Twitt" /> </a>
</div>