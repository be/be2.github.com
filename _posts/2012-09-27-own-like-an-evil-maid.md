---
layout: post
title: "Own like an evil maid"
description: "simple 512-byte MBR program that pretends to be Windows CHKDSK"
category: cs
tags: [bootloader, evil maid, windows, CHKDSK]
---
{% include JB/setup %}


Have you ever seen a movie where a hot spy lady pretends to be a maid just to discover the vilain's secrets? Well, the idea behind an "evil maid" attack is that someone, as the cleaner (aka, maid) sticks a SD card with the bootloader into somebody's PC when they aren't around. After a while you go back, recover it, and own him.

From the github page:

>This is s simple 512-byte MBR program that pretends to be Windows CHKDSK. It asks the user for a password, writes that password back to the media it booted from, renders that media unbootable, and reboots.

For instructions on how to assemble the program, install on a disk and extract the saved password @[AlexWebr](https://github.com/AlexWebr/evilmaid_chkdsk)

Wikipedia entry on [bootkits](http://en.wikipedia.org/wiki/Rootkit#Bootkits).