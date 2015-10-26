---
title: That Nasty Firefox Extension
author: Tim Tutt
layout: post
permalink: /2009/02/26/that-nasty-firefox-extension/
categories:
  - Tech Ed
tags:
  - ad.clickweb
  - adware
  - google redirects
  - google search ads
  - malware
  - search engine redirect
  - virus
---

So there has been a lot of noise on the interwebs about this new &#8220;malware&#8221;/&#8221;virus&#8221;/&#8221;worm&#8221; that apparently no anti-virus software has been able to detect or remove recently. Last week I was infected with this nasty little thing and it was really starting to piss me off. I had been searching madly across the Internet (using cached search pages, a little work around this bug) to try and find the solution to this little issue. I also ran every piece of malware and anti-virus software I have&#8230; which by the way is a lot.

After my holy-trinity of virus-killing software (Malwarebytes, Avira, and CCleaner) found nothing numerous times I was starting to get excessively frustrated. Then I came across a forum posts of Firefox users who all had the same issues&#8230; Turned out this was a Firefox specific problem (which of course I wouldn&#8217;t know because I never use IE, I assumed all was infected).

One user (bless him) said that this was an extension related issue, just find the extension folder that was modified around about the date you noticed the infections and remove it. Restart Firefox and it works without the problems. Me and my curious self&#8230; decided that I wanted to look at the code of this little thing.

So I dug in and copied the XUL (XML User Interface Language) file and opened it to see the code. These files, as a side, are used to change the user interface of Firefox, and are the reason that some extensions can make web pages change and do all the weird and cool things that we all seem to love&#8230; They are also the reason for my frustration over the past week..

So I open the file and look at the code and its very simple actually&#8230; Here are a few lines&#8230;

<span style="color:#ff00ff;">if( loc.match(/google\..+\/search.*[&\?]q=([^&]*)/)){<br /> keyword = RegExp.$1;<br /> engine = &#8216;google&#8217;;<br /> //    } else if(loc.match(/search\.ua.+[&\?]q=([^&]*)/)){<br /> //        keyword = RegExp.$1;<br /> } else if ( loc.match(/search\.yahoo.*search.*[&\?]p=([^&]*)/)){<br /> keyword = RegExp.$1;<br /> engine = &#8216;yahoo&#8217;;</span>

<span style="color:#000000;">There are actually a number of lines like this for every single browser. Simple regular expressions and checks the search engine. If it matches, then you are going to see these random redirects to some adserver, then to a page of their choosing&#8230; Found this little variable, which is apparently the server your requests are redirected to and changed. </span>

<span style="color:#000000;"><span style="color:#ff00ff;">var __d = &#8220;http://v1.adwarefeed.com/ffjs.php?u=1145892647-2942932799-2535655826-377724549a=998&s=3&v=icv270109ff&e=&#8221;;</span></span>  
I love the Internet, but I hate stuff like this out there. Anyways, Removal instructions are simple:

1.) Go to: %Mozzila Firefox%\extensions\

2.) Delete folder **xxxxx **where **xxxxx** is something like {CAFEEFAC-0016-0000-0011-ABCDEFFEDCBA} and has a modified date around the time you got infected.

3.) Restart Firefox, problem solved.

And if you&#8217;re anything like me, look at the code for yourself and see exactly what it was doing&#8230; While nasty, its actually a pretty neat trick. Useful if you want to say&#8230; spy on someone using your internets. Oh, Change passwords if you&#8217;ve used any while being infected. Can never be too safe.

