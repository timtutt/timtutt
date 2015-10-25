---
title: Can Policy and Power Be Mutually Exclusive?
author: Tim Tutt
layout: post
permalink: /2010/02/08/can-policy-and-power-be-mutually-exclusive/
idptt_tweeted:
  - 1
categories:
  - Uncategorized
tags:
  - access
  - authority
  - authorization
  - authorization and access
  - permission
  - policy
  - power
  - power and authority
  - security
  - security policy
  - UN
  - united nations
---
<div class="twttr_button">
  <a href="http://twitter.com/share?url=http://www.timtutt.com/2010/02/08/can-policy-and-power-be-mutually-exclusive/&text=Can+Policy+and+Power+Be+Mutually+Exclusive%3F" target="_blank" title="Click here if you like this article."> <img src="http://www.timtutt.com/wp-content/plugins/twitter-plugin/images/twitt.gif" alt="Twitt" /> </a>
</div>

Two nights ago while snowed in, one of my roommates and I got into one of those interesting political discussions that you always seem to have while in college.  It started off as a simple enough debate about whether or not capitalism is fair, and if not what type of economic system would work better.  As is the case with every political discussion, this did not end with just the discussion on economic systems. At some point we found ourselves discussing the United Nations and its authority to enforce any agreements made among the nations involved.  My roommate made an interesting point saying that while the UN may have authority they have no real power.  The UN itself does not have a body that it can use to enforce these policies, as it requires the participation of members of the UN to actually enforce.  Additionally, these members have the option to elect not to participate in enforcing certain policies.  Without the participation of the major members, the UN virtually has now power. The question then becomes can you have the authority to create policy without the power to enforce it?

The question itself is not a new one at all, and is in fact one that I have considered in other scopes (particularly in the security policy arena), but this discussion we had got me thinking about the issue in a different way. I want to start by discussing authority and power as completely separate ideas briefly.

Authority implies having the right or authorization to do something, whether that just be the authorization to grant someone else permission to do something or, the authorization to actually perform a task yourself.  This can be seen in a wide range of examples, but to give a specific one, consider a DBA working with a group that requires limited access to information. That DBA may have the authority to grant CRUD permissions on specific tables, but may lack the authority to perform those CRUD operations his or herself.

Power, on the other hand, is more focused on someone having the ability to do something with or without the appropriate authorization. For instance, continuing with the prior example, a Data Analyst may have the ability to perform those CRUD operations once granted the authorization by the DBA; however, a hacker may also have the ability to perform these very same actions without having the appropriate authorization to do so.  To be clear, power has nothing to do with how the ability was obtained, but just the fact that the ability exists.  Instead of using a hacker, we could have used the DBA who may have the power to perform those CRUD operations, while lacking the authority to use them.

With a better understanding of authority and power, let&#8217;s take a look at policy.  A non-technical manager decides to implement a security policy for data access which restricts the DBA from performing any operations other than granting permissions to user approved by the manager.  The manager is implementing this policy because any unauthorized access to the information could be detrimental to the organization.  Bear in mind, that being non-technical, the manager has no way of enforcing this policy other than entrusting the DBA with the job of ensuring that only authorized users have access to this information.  The DBA has the power and authority to grant permissions.  The DBA also has the power to access this information, but according to the security policy he does not have the authority to access it.  How does the non-technical manager go about enforcing the policy effectively without having to just inherently trust the DBA?

An old saying is heard time and time again in the security world: &#8220;Trust, but verify.&#8221;  So the manager decides that he will do regular audits of who has accessed the data and require the DBA to provide these access logs on a weekly basis to ensure that the policy is indeed being enforced.  The DBA has the ability to alter these audit logs prior to sending this report, so this becomes an ineffective strategy very quickly.  The only other option this manager has is to hire someone whose job is to monitor access to data by all users including the DBA.  This will allow the manager to be informed of any unauthorized accesses and handle each case, but it only does so after the breach has occurred.  If this were mission critical or otherwise highly sensitive data, the damage would have already been done before the manager could take administrative action.

In this example, the real power to enforce the policy actually lies with the DBA not the manager.  The manager must trust some third-party to ensure that his policy is enforced.  Now this example has a solution, though it may not always be a feasible one.  The manager should only hire a DBA that he trusts absolutely to enforce this policy the way he sees fit.  What if the issue were instead, that users had a way to circumvent a policy.  A perfect example would be an organization that restricts users from loading executable files from external media to their machines.  The way this policy is enforced is by having as a part of a mandatory group of installed programs on the machines a Antivirus program that scans any attached media and quarantines any file that meets a specific set of criteria.  A user, intent on having a certain executable file loaded on their machine, circumvents the policy by turning off the Antivirus software until they can get the program loaded (real example).  The obvious solution is to prevent the user from being able to turn the Antivirus software off, but the user needs to have the ability to do this in special cases without having to go through hoops so you can not include this in your policy.  This is the Catch-22 that many policy makers find themselves in on a daily basis: having to give users power without authorization, or deny access without the power to prevent it.

I want to close the discussion from a technical standpoint with a few thoughts on how the issue can be addressed.  As technologist, we should be creating technology that allows policy makers to enforce whatever policies they want to make.  If that means getting as granular as the technology will allow you to get, then that is what needs to be done.  There is no reason from a technical standpoint that policy makers should not be able to enforce policies they make due to a lack of technical knowledge.  That being said, we must also be wary of allowing non-technical policy makers to make uninformed policy decisions in regards to technology.

More generally, it is still difficult to find a solution.  If an organization has no direct power to enforce a policy, do they actually matter?  At that point do the policies become just a mere suggestion?  If there is no consequence, that will be incurred due to the lack of power to enforce policies, then what stops the members affected by a policy from breaking it?  The technical issue can be solved by giving policy makers the power in a way that makes sense to them, but you cannot create power from thin air.  If the power to enforce a policy does not exist, the policy is nothing more than words.

This conversation can be taken somewhat literally, so I want to be clear on a few things. I do not advocate breaking policy just because policy can be broken.  To do so would be to support the breaking of laws that cannot be enforced and to promote illegal actions such as piracy.  What I am suggesting however, is that policy makers take a harder look at the policies they are trying to implement and only implement those which can be enforced.  This does not mean laws and policies have to be thrown out, just that they adapt to the powers that exist.

I&#8217;m interested to hear your thoughts on power and policy. Let me know what you think.

<div class="twttr_button">
  <a href="http://twitter.com/share?url=http://www.timtutt.com/2010/02/08/can-policy-and-power-be-mutually-exclusive/&text=Can+Policy+and+Power+Be+Mutually+Exclusive%3F" target="_blank" title="Click here if you like this article."> <img src="http://www.timtutt.com/wp-content/plugins/twitter-plugin/images/twitt.gif" alt="Twitt" /> </a>
</div>