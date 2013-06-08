---
title: Permanently remove updater from Google Earth
excerpt: All Exposé modes are controlled by the F3 key.
tags: mac
date: 2009-04-23 18:22
slug: permanently-remove-updater-google
author: Francisco Pinto
layout: post
location: Málaga, Spain
type: mac
---

There has been a fair amount of controversy around Google forcing users to install a background updater application before they can use Google Earth 5. A point of particular contention is that a user has no immediate control through the application interface to specify if or how often they want the Google updater service to activate.

As one can imagine, this has the potential to cause a world of hurt especially for people on limited internet connections. Personally, I just don’t like not having control over what my computer does; I say what software gets installed and when it gets run. Excuse me while I keep myself from getting carried away here and going on a big rant.

**Remove Google Earth’s ability to install the update service**

Locate your copy of Google Earth, Control-click on the application and choose Show Package Contents from the pop-up menu. Now remove the following two files, based on starting at the top of the application bundle:

- Contents/Frameworks/KeystoneRegistration.framework/Resources/install.py
- Contents/Frameworks/KeystoneRegistration.framework/Resources/Keystone.tbz

The first file is the python script used to install the updater service, while the second is a tar-bzip’d bundle that contains the updater service. If the source files aren’t there, Google Earth will be incapable of installing the updater service, no matter what you tell/told it on first run. 

**Remove the updater application and files installed by Google Earth** 

If you’ve already been running Google Earth 5, you may also wish to do the following after completing the first part of the hint. Remove the following folders/files:

- ~/Library/Google/GoogleSoftwareUpdate
- ~/Library/LaunchAgents/com.google.keystone.daemon.plist
- ~/Library/Caches/com.Google.Keystone.*
- ~/Library/Logs/GoogleSoftwareUpdateAgent.log

The first being the Google update service, the second the launchd plist that specifies when to run the service, third any items already downloaded by the google update service, and fourth the log file from the update service. 

**Addendum** 

If you’ve followed thus far, you should have successfully removed the Google Update service from your Mac, and prevented Google Earth from being able to re-install the software. Note that other Google software may also use/install the Google Update service. I haven’t researched that far, and so this hint applies to those only using Google Earth 5 and no other Google software. If all you wanted to do was remove the update service from Google Earth 5, you can stop reading now. If you’re of the curious type, the following may be of interest to you, and is provided for informative purposes only. 

Those with the ability to read programming code, particularly Python, may wish to peruse the install script to see exactly what happens when the software in installed. If you do, you may notice that providing the —nuke flag when running the script will remove the software and the launchd plist; this of course doesn’t stop Google Earth re-installing it at next launch. It also doesn’t remove the log, nor the update cache. 

For some reason, the Keystone Registration framework also includes copies of the bundle and install script at the following locations, using the same working directory as part one of the above hint: 

- Contents/Frameworks/KeystoneRegistration.framework/Versions/A/Resources/
- Contents/Frameworks/KeystoneRegistration.framework/Versions/Current/Resources/ 

Normally, …/KeystoneRegistration.framework/Versions/Current is a symlink to …/KeystoneRegistration.framework/Versions/A, and …/KeystoneRegistration.framework/Resources is a symlink to …/KeystoneRegistration.framework/Versions/A/Resources. 

Not sure what’s going on here, but it seems a bit redundant to have three copies of the same files. Nonetheless, removing the items in the above hint is sufficient in preventing the installation of the service.
