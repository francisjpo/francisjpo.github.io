---
title: Compress and uncompress in *NIX
excerpt: Although I have done it many times, I always forget how to compress a file or folder using the command line.
tags: mac, sysadmin
date: 2006-06-06 15:06
slug: compress-uncompress-unix
author: Francisco Pinto
layout: post
location: Málaga, Spain
image:
color:
---

Although I have done it many times, I always forget how to compress a file or folder using the command line. So this entry will be a receipt in order to quickly look it up.

The reason why I use the command line is that I like keeping file permissions — read, write, execute — and that can only be possible using *tar*. [^fn1]

{% highlight bash %}
**tar.gz files**
$ tar czfvp filename.tar.gz folder	# compress
$ tar xzvfp filename.tar.gz	# uncompress
$ tar tzvf filename.tar.gz	# show content
{% endhighlight %}

{% highlight bash %}
**tar.bz2 files**
$ tar cjfvp filename.tar.bz2 folder	# compress
$ tar xjvfp filename.tar.bz2	# uncompress
$ tar tjvf filename.tar.bz2	# show content
{% endhighlight %}

{% highlight bash %}
**zip files**
$ zip filename.zip files	# compress
$ unzip filename.zip	# uncompress
$ unzip -v filename.zip	# show content
{% endhighlight %}

{% highlight bash %}
**rar files**
$ unrar xv filename.rar	# uncompress
$ unrar tv filename.rar	# show content
{% endhighlight %}


[^fn1]: At the same time, I have included zip and rar files. They are not my favourites, but they can be useful.
