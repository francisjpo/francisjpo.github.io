---
title: How-To hide Growltunes toolbar icon
excerpt: You can get rid of the GrowlTunes toolbar icon.
tags: mac
date: 2008-12-16 17:22
slug: hide-growltunes-toolbar-icon
author: Francisco Pinto
layout: post
location: Málaga, Spain
image:
color:
---

You can get rid of the GrowlTunes toolbar icon. Open **Terminal.app** and type:

{% highlight bash %}
$ defaults write com.growl.growltunes GrowlTunesWithoutMenu -bool YES
{% endhighlight %}

Restart GrowlTunes.app *et voilà*.
