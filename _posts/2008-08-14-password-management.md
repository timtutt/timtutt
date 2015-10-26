---
title: Password Management
author: Tim Tutt
layout: post
permalink: /2008/08/14/password-management/
categories:
  - Tech Ed
tags:
  - cookie
---

I was talking to my co-worker the other day and she was telling me about this &#8220;amazing&#8221; tool she found that manages your passwords, and all you have to do is remember one. I immediately knew what she was referring to and said that had been out for a while and that just about all browsers had that capability&#8230; I realized today that I spoke too soon. What I should have said was just about all *decent* browsers have that capability.

What I failed to realize at the time was that Microsoft Internet Explorer is still way behind the times. I&#8217;m used to using Firefox, and I knew for a fact that it had that ability, so naturally (and mistakenly) I assumed that Microsoft would have embedded such a simple feature into their product&#8230; I assumed wrong. Now before this article turns into a Microsoft bashing, or an article about why EVERYONE should use Firefox over IE (which you should: [Get Firefox][1]), I&#8217;m going to stop this intro and move into the meat of this &#8220;tech ed&#8221; article.

Password management comes with a few obvious pitfalls and benefits that I&#8217;ll go over here. Regardless of what browser you use, you&#8217;ve all undoubtedly seen those sometimes annoying pop-ups or check boxes asking you if you want to save your user name and password. These features are there for users out of convenience, but have a few drawbacks. What you end up with is saved credentials so that you do not have to log back into a site that you visit regularly. Now if you are the only person that ever uses this computer under that login name then this works great. The issues occur when you have multiple computers using the same computer to access the internet. If you save your passwords for all of your e-mails, blogs, bank accounts, social networking sites, etc&#8230; then the next person that uses your computer has access to all of this information.

Now password management comes in one of two forms; that is, browser based and cookie based. When you login to most e-mail applications on a web site there is normally a little checkbox that ask if you want to remain logged in. When you select that checkbox and login, what happens is a little file called a &#8220;cookie&#8221; (these are used for a number of things, there will probably be a separate article on this) is placed onto your computer. Now anytime you access that website no matter what browser, it attempts to read from that cookie to get your login credentials so that you don&#8217;t have to type them back in. You should always pay attention to these checkboxes because sometimes they are automatically selected and you have to deselect them. Because of security reasons, some sites like Yahoo are getting smarter and putting time limits on those cookies. So after a while it will expire and you&#8217;ll be forced to remember your password, but remember they do this for protection of your information.

The other type of password management is browser based management. Anytime you see a pop-up asking if you want (insert your browser here) to store your password for the future, that&#8217;s browser based management. The major benefit that browser based management has over cookie based management, is that with browser based management, you know exactly what is being stored &#8211; your credentials for that website, and nothing else &#8211; and there is no way for a remote attacker to obtain any additional information. If you want more detail on that, wait for another article.

The feature that I mentioned earlier that Firefox has is a nifty little tool that takes the benefits of password management and minimizes the pitfalls. If you are using Firefox, go to Tools->Options->Security. You will see two checkboxes. One says &#8220;Remember passwords for sites&#8221; and the other says &#8220;Use a master password&#8221;. Now by default, &#8220;Use a master password&#8221; is not selected. So if you have saved any of your passwords, then anyone that uses the browser can access the sites where you have information stored. If you use a master password, then you merely have to remember a single password, so anytime you bring up Firefox, you put that password in and you can freely browse the websites where you previously saved your information without having to log in. If you do not put in that password, you will have to log in to each individual site. The only issue with this method is the security of that master password. If anyone else knows that password, then they too can access all of your sites.

One other method of authentication on websites that I have yet to mention is something referred to as single sign on. It is a concept that is used throughout enterprises and is starting to catch on in the web, but is still in its infancy when it comes to websites. Certain providers such as [OpenID][2] allow users to link their OpenID account to other websites that they use so that they only have to remember the OpenID password. Currently, you do not see this technology being used on major sites such as Banks, or Online stores because of security reasons, but the social networking arena is really taking to it.

So that&#8217;s about all I have on password management&#8230; Hope you all enjoyed this edition of Tech Ed &#8211; I&#8217;ve gotta get a better tag line.


 [1]: http://www.mozilla.com/en-US/firefox/
 [2]: http://www.openid.net
