---
layout: post
title: "Compiling OpenEmu on OSX"
description: "Compiling OpenEmu From Source on MacOSX"
category: programming
tags: [osx, openemu, xcode, git, nintendo64]
---
{% include JB/setup %}

![ninendo64](https://dl.dropboxusercontent.com/u/5666518/pic-pref-th.png)

Miss your old Nintendo 64 games like Diddy Kong Racing, Super Mario 64, Mortal Kombat Trilogy or Donkey Kong? Maybe you should give OpenEmu a try. To compile the emulator on OSX you'll need to do the following:

First of all you'll need the latest copy of [Xcode](https://itunes.apple.com/gb/app/xcode/id497799835). Download and install it.

Second, download the OpenEmu source code from github. You can easily do it by cloning their repository with [Github for Mac](http://mac.github.com/). Create an account, navigate to https://github.com/OpenEmu/OpenEmu and click the "Clone in Desktop" button. 

Once Git has finished cloning, browse to the 'OpenEmu' folder it cloned to (chose the folder before cloning).

Open the 'OpenEmu' folder and find the XCode project file called 'OpenEmu.xcworkspace'. Double click this file and it should open in XCode.

Now the XCode is opened and you should click on the long bar to the right of the 'Stop' button and select the correct 'Scheme'. Then select 'Build All' > 'My Mac 64 Bit'...

Finally click on 'Product' > 'Build For' > 'Profiling' in the menu bar and OpenEmu will now begin compiling.

Once XCode has compiled OpenEmu, simply search for OpenEmu.app in Finder, right-click on it and select 'Open Enclosing Folder'.

And now you can launch OpenEmu directly from this folder.

To add games you can try this amazing [torrent](http://www.mac-torrents.com/torrents.php?mode=details&id=5065d47f92da2d5a03e3820b9a2519c4d4199830)

Cheers! 

