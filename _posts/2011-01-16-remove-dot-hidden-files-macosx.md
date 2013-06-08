---
title: Remove dot hidden files in Mac OS X
excerpt: Easy clean up hidden files.
tags: mac
date: 2011-01-16 21:39
slug: remove-dot-hidden-files-macosx
author: Francisco Pinto
layout: post
location: Málaga, Spain
type: mac
---

Open **Terminal.app**:

{% highlight bash %}
$ dot_clean -mn ./
$ find . -name “.*” -exec rm -rf {} \;
{% endhighlight %}