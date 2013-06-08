---
title: Mac OS X maintenance
excerpt: Useful commands for Mac OS X maintenance.
tags: mac
date: 2008-12-03 20:21
slug: macosx-maintenance
author: Francisco Pinto
layout: post
location: Málaga, Spain
type: programming
---

Open **Terminal.app** and type:

{% highlight bash %}
$ sudo /usr/sbin/diskutil repairpermissions /
$ sudo /usr/sbin/periodic daily weekly monthly
$ sudo /usr/bin/update_dyld_shared_cache -force -root /
$ sudo /usr/bin/update_prebinding -force -root /
{% endhighlight %}

With these few lines and a restart, we can keep our systems — both PPC and Intel — clean and ready to do the hard work.