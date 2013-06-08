---
title: How to index new filetypes with Spotlight
excerpt: Sometimes I need to track fragments of code which filetype is not indexed by Spotlight.
tags: mac, sysadmin
date: 2006-05-01 14:34
slug: index-new-filetypes-spotlight
author: Francisco Pinto
layout: post
location: Málaga, Spain
type: mac
---

Sometimes I need to locate fragments of code which filetype is not indexed by Spotlight — mostly Ruby and Matlab — and I waste more my time looking for the file than locating the code itself. As they are usually plain text it is easy to index their content in Spotlight.

A proper solution is modifying **Info.plist** inside **SourceCode.mdimporter**, located in **/System/Library/Spotlight/** — which requires root privileges[^fn1].

You may add a line to the UTExportedTypeDeclarations key:

{% highlight bash %}
<key>UTExportedTypeDeclarations</key>
<array>
	<string>com.sun.java-source</string>
	<string>public.php-script</string>
</array>
{% endhighlight %}

To make the changes take effect, Spotlight has to check new filetypes:

{% highlight bash %}
$ mdimport -r /System/Library/Spotlight/SourceCode.mdimporter
{% endhighlight %}


[^fn1]: In these cases having installed XCode can be very helpful, since some plist files are pretty messy.
