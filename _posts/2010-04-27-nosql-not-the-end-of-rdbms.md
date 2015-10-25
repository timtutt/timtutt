---
title: 'NoSQL &#8211; Not The End Of RDBMS'
author: Tim Tutt
layout: post
permalink: /2010/04/27/nosql-not-the-end-of-rdbms/
idptt_tweeted:
  - 1
categories:
  - Application Development
  - Databases
  - Tech Ed
tags:
  - cloud computing
  - CRUD
  - Databases
  - distribtued
  - distributed database
  - document-oriented
  - Fold
  - key-value
  - Map
  - MapReduce
  - MySQL
  - no schema
  - NoSQL
  - PHP
  - RDBMS
  - Reduce
  - Relational Database Management Systems
  - Relational Databases
  - scalability
  - scaling out
  - scaling up
  - schema
---
<div class="twttr_button">
  <a href="http://twitter.com/share?url=http://www.timtutt.com/2010/04/27/nosql-not-the-end-of-rdbms/&text=NoSQL+-+Not+The+End+Of+RDBMS" target="_blank" title="Click here if you like this article."> <img src="http://www.timtutt.com/wp-content/plugins/twitter-plugin/images/twitt.gif" alt="Twitt" /> </a>
</div>

There has been a lot of noise on the web recently in regards to the death of relational database management systems.  This is not the first time there has been such sacrilegious chatter, but it is the first time that developers as a whole are really starting to pay attention to it.  There is good reason for everyone to start paying attention to the NoSQL movement, but it is **not** the end of relational database management systems.  That being said, in this article we are going to take a look at what exactly NoSQL is all about and how it can be beneficial.

Before we jump into NoSQL, let&#8217;s talk about relational database management systems (RDBMSes) and why they are, and have been used.  In a RDBMS a database is comprised of tables, which are comprised of rows and columns.  Each row of the table is considered a record with a value for each one of the columns (though some of those values may be blank or NULL). Relational databases currently run the world whether you are talking about an online e-commerce site, the next big Web 2.0 Social Networking fling, or major enterprise applications. It is a great way to keep unrelated information separate while preserving the ability to link to semi-related information pertaining to a specific user. In short, relational databases are great for **structured** data.  There is of course one major caveat to that fact&#8230; Your data has to be structured.

Anyone out there who has spent more than five minutes designing a database knows the pains of building a schema that is efficient for the task at hand.  Data modeling, despite what many may think is a non-trivial task. If you are thrown a large set of data about customers, products, and sales for a online retailer,  with relational databases you do not want to be storing all of that information in the same table. You want to keep your product information separate from your customer information, and separate from the sales transactions. There are a number of reasons you want to do this such as avoiding duplicate data, giving data context, scalability, and security of information to name a few.

**So what&#8217;s the problem? **

One of the major problems with relational databases is their limited ability to scale. You typically have to scale &#8220;up&#8221; instead of &#8220;out&#8221; to get better performance with databases that are hit on a very consistent basis. That is to say, you have to throw more ram, faster processors, and hard drives with better IO at the database server to get optimal performance versus spreading the load across multiple servers. Granted there are things like Memcached out there to assist with the scaling out issue, but it is not always going to be the most optimal solution.

Performance is another big one that needs to be addressed. Just about every relational database out there is stored on disk and as everyone knows, disk IO operations (unless you&#8217;re using SSDs) are really expensive.  With transactions occurring constantly, these hits will eventually wear the disk down and require replacement, or at the very least be slow with large concurrent user bases.

There is also, of course, the issue of a relational model not always being necessarily the right model for the job. Think business intelligence and reporting tools. These tools just want a view of the data for analytical purposes. In order to get the information they want, large queries that run across multiple tables are written with various joins and specific rules for lack of information etc.. At the end of the day this is a cumbersome process that takes a large hit on the database for an analytics tool.

**Enter &#8220;NoSQL&#8221;**

I want to start by saying NoSQL is a terrible name for this movement. To be honest this movement is not really anything new, its a rehashing of old ideas that is making leaps and bounds due to the current tech-buzz: cloud computing.  The idea is to move away from relational databases and move into unstructured databases. For a lot of DBAs out there this is going to sound excessively sacrilegious and you may want to hang yourselves while reading it, but give me a few minutes and I promise you&#8217;ll regain your bearings.

Here goes: Unstructured databases lack the concept of tables. In fact, they lack the concept of columns, or schema in any sense. There is no data modeling with unstructured databases. You have one table filled with records with varying numbers and names for fields in each record. (I told you, give me a few minutes, keep breathing, you can get through this).  The idea is data does not always need to have a specific structure. There is no point in having fields in a record that have no value. That&#8217;s just taking up space (space is still reserved for a record, used or not in relational databases).

Indexing essentially becomes a hash map. Key value pairs. You give it a key, and it returns a record (or document) that has whatever fields it has and nothing more. Again this is all in one table. Think about this from a large dataset perspective. I need to get information in a single record. I know exactly where that record is in my dataset thanks to my key. Searching for it is a trivial task. We&#8217;re not doing the unnecessary look ups for data as done with B-Trees (how most indexing systems in relation databases are done).

&#8220;NoSQL&#8221; databases are being designed to reside on multiple servers. Think Amazon&#8217;s EC2. Large datasets in the &#8220;cloud&#8221; for processing. Replication is literally built into these systems, so no more of the master/slave type deal. Most of these NoSQL databases are being built to run in memory with the ability to persist on disk. That means less disk IO operations, thus saving you money in the long run. Virtual servers with shared data on a SAN anyone?

Another big benefit that I see with NoSQL is from an application design perspective. When designing applications, you can be a bit more generic. There is no need to know about the schema of a database. You build the application generically based on the data you receive from a particular record. Some app developers out there might be bothered by this concept, but if you start to really think about it, it saves you time in the long run. Reusable code for varying datasets.

**This is not the end of RDBMS**

All that said &#8211; this is not the end for relational databases. Not even by a long shot. What we have here is an opportunity to look at a different way to handle large datasets. A way to really take advantage of cloud computing. Should people be paying attention to the &#8220;NoSQL&#8221; movement? Yes, but let us make sure we are paying attention to it for the right reasons. From a development standpoint, this is another tool we can add to our arsenal. It is a powerful tool, but one that comes with a huge responsibility.

That responsibility is knowing when to use it. &#8220;NoSQL&#8221; databases are not always the answer. Relational databases will more times than not solve the problems you are looking to solve. It happens a little to often that we tend to hop on the bandwagon of technologies just to be early adopters. I don&#8217;t want to see a ton of &#8220;NoSQL&#8221; fanboys out there throwing it at everything they see. Be aware that &#8220;NoSQL&#8221; exists, and that it can potentially be very useful in the right situations.

<div class="twttr_button">
  <a href="http://twitter.com/share?url=http://www.timtutt.com/2010/04/27/nosql-not-the-end-of-rdbms/&text=NoSQL+-+Not+The+End+Of+RDBMS" target="_blank" title="Click here if you like this article."> <img src="http://www.timtutt.com/wp-content/plugins/twitter-plugin/images/twitt.gif" alt="Twitt" /> </a>
</div>