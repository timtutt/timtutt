---
title: Rackspace Cloud And Domain Transfers
author: Tim Tutt
layout: post
permalink: /2012/05/01/rackspace-cloud-and-domain-transfers/
idptt_tweeted:
  - 1
wpsd_autopost:
  - 1
categories:
  - Application Development
  - DNS
  - security
  - Server Setup
  - Tech Ed
  - Web Development
---
<div class="twttr_button">
  <a href="http://twitter.com/share?url=http://www.timtutt.com/2012/05/01/rackspace-cloud-and-domain-transfers/&text=Rackspace+Cloud+And+Domain+Transfers" target="_blank" title="Click here if you like this article."> <img src="http://www.timtutt.com/wp-content/plugins/twitter-plugin/images/twitt.gif" alt="Twitt" /> </a>
</div>

For starters, I actually had not planned on writing this article&#8230; Sometimes topics just fall into your lap, and you can do nothing else, but move on them. This one is going to be a little more directed than usual as it is inspired by an event that occurred today. For my more technical readers you can skip over the next three paragraphs to get to the meat of this story while explain a few things like DNS to everyone else.

Here goes a quick crash course on the Internet, IP Addresses, Domains, and DNS. Contrary to popular belief the Internet is not run by a bunch of elves running around putting &#8220;cookies&#8221; on your machine. In actuality, what happens is your computer sends things called packets across the huge network that is the Internet.  These packets contain data with your requests or responses to and from servers and other devices on the Internet. Now usually you&#8217;ll type www.icanhascheezburger.com into your browser (i.e. Internet Explorer, Firefox, Safari, Chrome or the like) and magically get the days latest cute kittens, but how does this work?

Every device on the Internet has something called an Internet Protocol (IP) Address (for the sake of simplicity we won&#8217;t get into IPv6 vs IPv4 here today). An IP Address is effectively your online phone number. For instance, the IP address for this website is 69.195.75.87. When a computer makes a request to another computer it is actually using the IP address. But wait, you didn&#8217;t type that into your browser, so how did it know how to find me? That&#8217;s where DNS comes in. Domain Name System (DNS) is essentially the phone book for your computer on the Internet. Your computer shoots out a request and says &#8220;Hey which of you DNS servers can tell me where to find timtutt.com&#8217;s phone number?&#8221; One of them responds with a &#8220;Hey that&#8217;s me, his phone number is 69.195.75.87.&#8221; Once your computer has the phone number it can appropriately route packets across the Internet to serve you the content you want.

Now let&#8217;s look at this from the other side. When I purchased by domain from my registrar, I had to point it at some name servers and say &#8220;Hey name servers, you&#8217;re responsible for telling the world what the phone number is of the computer I assign this domain to.&#8221; Without getting into too many details &#8211; A Name records are the records that tell the name servers what the phone number is. So I add an A Name record to the DNS service telling it that timtutt.com is at 69.195.75.87, which is the IP address of the server that I&#8217;m hosting this website on. **Typically**, when I purchase that domain and point it to name servers, the only account that can change the IP Address of my domain is me by modifying the A Name record. All of this is very simplified, but it gets the point across.

Now that we are all caught up, let&#8217;s get to my day. A few days ago, I decided I wanted to use Rackspace&#8217;s Cloud Servers for some random development projects and such that I was working on. I&#8217;ve used Rackspace in the past, love their support, the management console is great for rapid deployment of cloud servers, full control, prices are great etc&#8230; Now I&#8217;ve got about 10 domains with Bluehost (great host btw). I wanted to move some of those over to Rackspace so I could just manage domains and servers in the same place. Before I start rambling, let me just allow you to read the conversation I had with Rackspace support earlier today (scrubbed only to protect identity of support member):

&nbsp;

> Welcome to the Rackspace Cloud! My name is <redacted>, how may I help you?  
> <redacted>: Hi Tim!  
> Tim Tutt: Hi <redacted>,  
> Tim Tutt: I just spoke with one of your other support members about transferring a domain of mine to rackspace cloud servers  
> Tim Tutt: they referenced a document, and in reading through it, I seem to be missing a step to bind a domain to my account and my account only.  
> <redacted>: Can you post the link you were provided?  
> Tim Tutt: It says I need to point to rackspace&#8217;s name servers, and then add an A name record in DNS, which is fine, but couldn&#8217;t in theory someone else add an A name record pointing my domain to their servers?  
> Tim Tutt: <a href="http://www.rackspace.com/knowledge_center/content/transferring-your-domain-to-Rackspace-Cloud" target="_blank">http://www.rackspace.com/<wbr>knowledge_center/content/<wbr>transferring-your-domain-to-<wbr>Rackspace-Cloud</wbr></wbr></wbr></a>  
> Tim Tutt: I&#8217;m assuming I&#8217;m just missing a step or it&#8217;s not documented.  
> <redacted>: Of course!ß  
> <redacted>: To answer your question, yes  
> <redacted>.: you could update the DNS which your current DNS provider  
> Tim Tutt: right &#8211; that was my other option if this turned out to not be a viable solution  
> <redacted>: understood.  
> Tim Tutt: so to be clear &#8211; someone with another rackspace account could add an A name record before me and point to their servers if I pointed the domain to the rackspace dns servers?  
> <redacted>: Correct.  
> <redacted>: That wouldn&#8217;t be very nice but its possible  
> Tim Tutt: Okay got it &#8211; Well thanks very much. That makes my decision easy.

Yes, you read that right&#8230; Essentially in using the Rackspace name servers for my domain, I am giving the ability for anyone with a Rackspace cloud account to hijack my domain. This completely floored me. How could a vulnerability so obvious exist in a provider that is so well known and trusted? To their credit, I am very impressed that Rackspace knew and were honest about this vulnerability, but it is still one that is hard to overlook.

In talking to some buddies of mine, Rackspace is not the only offender. Slicehost has a similar issue. What is really concerning here is the fact that this is not a hard issue to fix. Imposing a validation step to see if a domain is associated with a particular account is a trivial task.  Additionally, validating user ownership of a particular domain is also a trivial task so the association should also be easy.  It tends to amaze me when such large companies make mistakes like this one.  They have a number of resources at their disposal and lots of technical talent, yet they lack the ability to think about situations that compromise security.

Large organizations focus on implementing best security practices to ensure the safety and security of information and property of their customers, but the fact of the matter is even the most advanced of systems won&#8217;t help if there are bad practices in the most simple pieces of the system. Security should be focused on in every aspect of a system not just the major parts that everyone pays attention to. This seemingly small issue is actually a major vulnerability. Hopefully Rackspace and others take care of issues like this one. I&#8217;d like to see less simple issues like this out there from major providers and vendors.

&nbsp;

<div class="twttr_button">
  <a href="http://twitter.com/share?url=http://www.timtutt.com/2012/05/01/rackspace-cloud-and-domain-transfers/&text=Rackspace+Cloud+And+Domain+Transfers" target="_blank" title="Click here if you like this article."> <img src="http://www.timtutt.com/wp-content/plugins/twitter-plugin/images/twitt.gif" alt="Twitt" /> </a>
</div>