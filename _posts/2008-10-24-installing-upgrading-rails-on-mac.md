---
title: Installing & upgrading Rails on Mac
excerpt: Since Rails is actually built-in to Leopard, we only need to update some gems.
tags: mac, sysadmin, rails
date: 2008-10-24 12:47
slug: installing-upgrading-rails-on-mac
author: Francisco Pinto
layout: post
location: Málaga, Spain
image:
color:
---

Since Rails is actually built-in to Leopard[^fn1], we only need to update the gems[^fn2] :

{% highlight bash %}
$ sudo gem update rails -y
$ sudo gem update rake -y
$ sudo gem update activerecord -y
$ sudo gem update activesupport -y
$ sudo gem update actionpack -y
$ sudo gem update actionmailer -y
$ sudo gem update activeresource -y	# or
$ sudo geminstall activeresource -y
{% endhighlight %}

If we want to remove older versions:

{% highlight bash %}
$ sudo gem cleanup
{% endhighlight %}

Updating our projects is our last step:

	- Edit **project/config/environment.rb** and set RAILS_GEM_VERSION to the new version you have just updated

{% highlight bash %}
$ rake rails:update
{% endhighlight %}

[^fn1]: [How to install on Tiger](http://wiki.rubyonrails.com/rails/pages/HowtoInstallOnOSXTiger).
[^fn2]: For more information: [Wiki Ruby On Rails](http://wiki.rubyonrails.org/rails/pages/HowtoUpgrade).