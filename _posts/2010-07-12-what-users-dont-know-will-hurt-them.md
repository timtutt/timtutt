---
title: 'What Users Don&#8217;t Know Will Hurt Them'
author: Tim Tutt
layout: post
permalink: /2010/07/12/what-users-dont-know-will-hurt-them/
idptt_tweeted:
  - 1
categories:
  - Application Development
  - Privacy
  - security
  - social networking
  - Tech Ed
tags:
  - college people search
  - documentation
  - end-user education
  - end-users
  - facebook privacy
  - hokie stalker
  - Privacy
  - security
  - settings
  - social engineering
  - user education
  - user experience
  - user knowledge
  - user security
  - Users
  - Virginia Tech
  - VT People Search
---

There&#8217;s an old saying, &#8220;ignorance is bliss&#8221;, that I&#8217;d like to add an addendum to today. The quote should be &#8220;Ignorance is bliss, until that ignorance hurts you&#8221;. In the IT world we have the tendency to build systems to the specifications provided by the &#8220;customer&#8221;. I quote customer like that because although there is usually a requirements group that provides the specifications to us, the real customer of the applications that we build are the end-users. (As a complete aside &#8211;  I&#8217;ve never been a fan of requirements groups. They rarely get the customer requirements right, and can never really explain why the end-user &#8220;needs&#8221; something. Another conversation for another day.)

I bring this up because usually what happens is a number of requirements are defined, the system is built to those specifications, the end-users are given a training on the most common features, and are pointed to documentation that they will never read for more advanced features. Even worse is when a user is &#8220;voluntarily&#8221; enrolled in some system as a part of some contract that they signed. The worst case is when a user signs up for a system, and is completely unaware that their information is also being used by several other systems. Users are often times harmed by not knowing how to protect themselves in these systems, or when they do not know what is in the realm of the possible.

Here&#8217;s just one specific example. Recently, I was planning on getting a birthday present for a friend of mine from college. I knew she was going to be at her parents place for her birthday, so I wanted to have the present sent to her home. The problem with that was I didn&#8217;t know her home address. Virginia Tech has a system that the students typically refer to as &#8220;Hokie Stalker&#8221;. You can search for a person by name and it returns their local address, home address, major, phone numbers, and e-mail address if they have not elected to suppress that information. The system is actually a public system, so anyone can go to the Virginia Tech website and search for any student and get all of that same information.

Needless to say, she got her present, but was curious as to how I got her home address. I explained it to her, and then explained that she could suppress it by clicking a checkbox in her account. The problem here was two-fold. She was unaware that I could even get that information and also unaware that she could hide it. Luckily, I was a friend just trying to send a gift, but the situation could have been a lot worse. Just by having a name, I could launch a very effective social engineering attack on some unknowing student. Knowing a major, a home address, the school they attend, and an e-mail address, I can make myself sound like a valid authority and request additional information.

A more interesting example deals with security in browsing the web. It is common these days that users know to look for the little lock in the bottom of their browser before entering personal information or credit card details, but they don&#8217;t really understand what that lock means. They assume that if the lock is there, then the site is secure and they can safely enter information. They also know to look for the &#8220;https&#8221; in the URL bar of their browser. While they know to make these checks, one thing that users are still very bad about is reading pop ups about security certificates. A user is trying to get to a site and this annoying pop-up prevents them from getting there &#8211; the auto-reaction is to click &#8220;Confirm Security Exception&#8221;. The user does not understand that a website can sign it&#8217;s own certificates and that if they accept these certificates, the browser will do as they say and treat this site as trusted thus showing them that lock that makes them feel all warm and fuzzy inside.

Browsers have done their part in attempting to explain to users what they are doing, but unless the user is security conscious, they don&#8217;t bother reading it. Some things are just beyond our control. Sure we can provide and require certain security trainings on the job, which hopefully employees will take and apply in their personal lives, but not every user of the Internet is granted these learning experiences. There are several other examples of users being unaware of how systems actually function and how these things can hurt them. Facebook privacy is one that we&#8217;ll leave alone today because it&#8217;s almost like beating a dead horse with a stick, but the point is users lack of awareness can and will hurt them.

Whether it be someone using information the user could have hidden for malicious social engineering attacks or a website claiming to be a user&#8217;s bank by providing a self-signed SSL cert, users can and will be attacked when they are unaware of what is possible. The question is how do we protect them from every threat? Productivity would certainly be lost if we explained every system in full detail to every user. That is just not a feasible solution. Perhaps the answer lies in how we present documentation to users. If documentation is hidden underneath layers of pages, then we can expect that users will not find it. Should we make documentation apart of the entire user experience with hints and tip boxes? Would that deter users from using systems? It&#8217;s an interesting question that I do not have the answer to. I do know, however, that as long as users remain ignorant of certain features of the systems they use, they are more likely to be attacked.

