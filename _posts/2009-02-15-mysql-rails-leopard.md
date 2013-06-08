---
title: MySQL, Rails & Leopard
excerpt: A simple receipt in order to use MySQL on Rails.
tags: mac, sysadmin, rails
date: 2009-02-15 22:15
slug: mysql-rails-leopard
author: Francisco Pinto
layout: post
location: Málaga, Spain
type: programming
---

A simple receipt in order to use MySQL on Rails.

- Download MySQL for Leopard from [MySQL website](http://dev.mysql.com/downloads/mysql)

{% highlight bash %}
$ mysql_secure_installation
#install the gem mysql
$ sudo env ARCHFLAGS="-arch i386" gem install mysql --with-mysql-config=/usr/local/mysql/bin/mysql_config
#repair the gem install
$ cd /usr/local/mysql/lib && sudo ln -s . /usr/local/mysql/lib/mysql
#start/stop MySQL server
$ sudo /usr/local/mysql/support-files/mysql.server start/stop
{% endhighlight %}