---
title: Send to Readability from Google Reader
excerpt: Despite the fact that I am a satisfied Instapaper user, I found the new Readability integration in Tweetbot quite exciting.
tags: general
date: 2012-02-15 19:25
slug: send-to-readability-from-google-reader
author: Francisco Pinto
layout: post
location: Málaga, Spain
image:
color:
---

[Tweetbot](http://tapbots.com/software/tweetbot) for iPhone recently updated to 2.0 adding a new feature: now, when you open a link from within Tweetbot, you can view the linked page transformed into a cleaner and more readable version of itself.

Despite the fact that I am a satisfied [Instapaper](http://instapaper.com) user, I found this feature quite exciting so I decided to drop Instapaper for a while and give [Readability](http://readability.com) a chance.

So far, the lack of a native iOS app and integration with other applications was the reason I stayed with Instapaper, I am also a big fan of Marco Arment's work — Instapaper, [his blog](http.//marco.org) or [Build and Analyze podcast](http://5by5.tv/buildanalyze).

Apparently, there will be an iOS app coming in the near future and the integration with apps is making progress. Instapaper is already present in Google Reader as a *Send To* dropdown. I find this menu very useful and there is also a way to manually add Readability — both *Read now* and *Read later* — yourself:

- **Read now**[^fn1]
	- Open *Send to* settings page in Google Reader.
	- Create a *custom link* at the bottom of the panel.
	- Set name to *Readability now*.
	- Set URL to: *http://www.readability.com/read?url=${url}*.
	- Set Icon URL to: *http://www.readability.com/media/images/favicon.ico*
	- Save.

- **Read later**[^fn2]
	- Open *Send to* settings page in Google Reader.
	- Create a *custom link* at the bottom of the panel.
	- Set name to *Readability later*.
	- Set URL to: *http://www.readability.com/save?url=${url}*.
	- Set Icon URL to: *http://www.readability.com/media/images/favicon.ico*
	- Save.

[^fn1]: Articles aren't directly turned into readable mode. You need to click the *Readability view* link that appears in the article header.

[^fn2]: Articles aren't directly added to your Reading List. You need to click the *Yes, save to my Ready List* button.
