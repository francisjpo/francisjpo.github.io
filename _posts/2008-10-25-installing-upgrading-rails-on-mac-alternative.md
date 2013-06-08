---
title: Installing & upgrading Rails on Mac (alternative version)
excerpt: Using XCode.
tags: mac, sysadmin, rails
date: 2008-10-25 20:13
slug: installing-upgrading-rails-on-mac-alternative
author: Francisco Pinto
layout: post
location: Málaga, Spain
type: programming
---

XCode — default install — is a must.

{% highlight bash %}
	$ sudo gem update --system
	$ sudo gem install rails
	$ sudo gem update
	$ sudo gem cleanup
	$ gem list
{% endhighlight %}

Making gem cleanup twice should remove every old dependencies.

Before the update, if you want to give SOAP a REST, do:

{% highlight bash %}
$ sudo gem uninstall actionwebservice
{% endhighlight %}

You can get Gem is not installed in directory /Library/Ruby/Gems/1.8 after a gem cleanup. If you want to clean out the old version, you must uninstall every gem individually:

{% highlight bash %}
$ sudo gem uninstall --install-dir=/System/Library/Frameworks/Ruby.framework/Versions/1.8/usr/lib/ruby/gems/1.8 the_gem
$ sudo gem list -d the_gem will show you the installed versions of a gem.
{% endhighlight %}