---
title: 'Installing phpmyadmin and PHP 5.2.* on a Centos 5.2 Server (updated)'
author: Tim Tutt
layout: post
permalink: /2009/02/17/installing-phpmyadmin-and-php-52-on-a-centos-52-server/
idptt_tweeted:
  - 1
categories:
  - Programming
  - Server Setup
  - Tech Ed
  - Web Development
tags:
  - centos 5.2
  - MySQL
  - mysql-server 5.1
  - php 5.2
  - phpmyadmin 3.1.2
  - yum
---

So I spent the better part of last night (12-3:30am) trying to figure out just exactly how to get phpmyadmin installed on my Centos 5.2 Server. Now, I&#8217;m no dummy when it comes to linux, package management etc&#8230; But this was a task which apparently many other people have had trouble with. I finally gave up on it and went to bed, woke up this morning and went back to it&#8230; At which point I actually figured everything out and now have PHP 5.2.8 installed working with phpmyadmin 3.1.2 (which to day, all the most recent stuff) using mysql-server 5.1.31.

So here&#8217;s how I did it: Apparently the repositories that Centos 5.2 uses by default still have php 5.1.* so you can just do a <span style="color: #ff00ff;">yum update</span> or <span style="color: #ff00ff;">yum install</span> <span style="color: #ff0000;">php</span>. The first step here is to set up the Remi repository. He maintains a repository that has the most up to date version oh php and all of its extensions. You can set this up by doing the following:

<span style="color: #ff00ff;"><span style="color: #000000;">$</span> wget </span><span style="color: #ff0000;">http://download.fedora.redhat.com/pub/epel/5/i386/epel-release-5-3.noarch.rpm</span>

<span style="color: #ff00ff;"><span style="color: #000000;">$</span> wget</span><span style="color: #ff0000;"> http://rpms.famillecollet.com/el5.i386/remi-release-5-7.el5.remi.noarch.rpm </span>

<span style="color: #ff00ff;"><span style="color: #000000;">$</span> rpm -Uvh <span style="color: #ff0000;">remi-release-5-7.el5.remi.noarch.rpm epel-release-5.3.noarch.rpm</span></span>

<span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;">This will set up the Remi repository for yum. By default it is disabled so you&#8217;ll have to use the <span style="color: #ff00ff;">&#8211;enablerepo</span> option with yum when you are using it to install or update anything. So in order to update to php 5.2.* you just say:</span></span></span>

<span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;">$ <span style="color: #ff00ff;">yum &#8211;enablerepo=remi install <span style="color: #ff0000;">php</span></span></span></span></span>

<span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;">To verify that you have php 5.2.8 installed issue a</span></span></span></span></span></span>

<span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;">$ <span style="color: #ff00ff;">php -v</span></span></span></span></span></span></span>

<span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;">And you&#8217;ll get a response like:</span></span></span></span></span></span>

<span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff0000;">PHP 5.2.8 (cli) (built: Dec  9 2008 14:11:33)<br /> Copyright (c) 1997-2008 The PHP Group<br /> Zend Engine v2.2.0, Copyright (c) 1998-2008 Zend Technologies</span></span></span></span></span></span></span>

<span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff0000;"><span style="color: #000000;">At this point I assume you already have mysql and mysql-server installed and configured. If not just issue:</span></span></span></span></span></span></span></span>

<span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff0000;"><span style="color: #000000;">$ <span style="color: #ff00ff;">yum &#8211;enablerepo=remi install</span> <span style="color: #ff0000;">mysql-server</span></span></span></span></span></span></span></span></span>

<span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff0000;"><span style="color: #000000;">It will install all of the necessary dependencies including mysql. Configuring mysql server using mysqladmin is actually out of the scope of this but there are plenty of tutorials online for that. Make sure you set up your   and passwords for accessing it otherwise you&#8217;ll have issues later.</span></span></span></span></span></span></span></span>

<span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff0000;"><span style="color: #000000;">Now, you&#8217;ll want to install php-mysql. Again use the remi repository for this, otherwise you&#8217;ll end up with tons and tons of dependency issues. Trust me, I learned this the hard way&#8230;</span></span></span></span></span></span></span></span>

<span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff0000;"><span style="color: #000000;">$ <span style="color: #ff00ff;">yum &#8211;enablerepo=remi install</span> <span style="color: #ff0000;">php-mysql</span></span></span></span></span></span></span></span></span>

<span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff0000;"><span style="color: #000000;">This will install the mysql.so module for you and add it to php.ini so you don&#8217;t need to add the extension=mysql.so. It does the same for mysqli. </span></span></span></span></span></span></span></span>

<span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff0000;"><span style="color: #000000;">So now you&#8217;ve got everything you need set up properly, so install phpmyadmin. Get the tar ball from the server, extract it somewhere in your htdocs folder, create a system link called phpmyadmin.  Go into the phpmyadmin and create a folder called config. Issue:</span></span></span></span></span></span></span></span>

<span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff0000;"><span style="color: #000000;">$ <span style="color: #ff00ff;">chmod o+rw</span> <span style="color: #ff0000;">config</span></span></span></span></span></span></span></span></span>

<span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff0000;"><span style="color: #000000;">Now because you&#8217;ve already set everything else up, you won&#8217;t receive the errors that I got on my first attempts. Now go to http:/www.yoursite.com/phpmyadmin/setup and follow the steps there. It&#8217;s a very nice little graphical interface that helps you set the configuration file. After this is done, move the config.inc.php file in the config directory to the head of the phpmyadmin directory. Then remove the permissions you set before:</span></span></span></span></span></span></span></span>

<span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff0000;"><span style="color: #000000;">$ <span style="color: #ff00ff;">chmod o-rw</span> <span style="color: #ff0000;">config</span></span></span></span></span></span></span></span></span>

<span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff0000;"><span style="color: #000000;">That&#8217;s it. Now you can go to http://www.yoursite.com/phpmyadmin and log in using your credentials for mysql-server. </span></span></span></span></span></span></span></span></span></span>

<span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff0000;"><span style="color: #000000;">Hope this saves everyone from running into all of the issues I had.<br /> </span></span></span></span></span></span></span></span></span></span>

<span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff0000;"><span style="color: #000000;"><br /> </span></span></span></span></span></span></span></span>

<span style="color: #ff00ff;"><span style="color: #ff0000;"><span style="color: #000000;"><br /> </span></span></span>

