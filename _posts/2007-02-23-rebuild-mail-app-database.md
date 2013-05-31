---
title: Rebuild Mail.app database
excerpt: How to easily speed up Mail.app.
tags: mac, sysadmin
date: 2007-02-23 11:43
slug: rebuild-mail-app-database
author: Francisco Pinto
layout: post
location: Málaga, Spain
image:
color:
---

After many email transactions — incoming, sent and deleted messages — Mail.app grows a SQLite database called *Envelope Index* with tons of no longer useful information. Every time Mail.app is started, this index is checked and updated. The more it weights, the longer it takes to load. *Envelope Index* can be found in **~/Library/Mail folder**.

As far as I know, there is only a way to clean up this information without removing useful data:

- Quit Mail.app.
- Open Terminal.app

{% highlight bash %}
$ cd ~/Library/Mail
$ sqlite3 Envelope\ Index
  sqlite> vacuum subjects;
  [Press Control+D]
{% endhighlight %}

- Quit Terminal.app


My *Envelope Index* was 14MB before the trick. Filesize has been decreased to 7MB[^fn1].

[^fn1]: It would be nice and easy to automate this trick an Applescript.
