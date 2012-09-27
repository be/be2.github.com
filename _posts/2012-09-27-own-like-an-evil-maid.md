---
layout: post
title: "Own like an evil maid"
description: "simple 512-byte MBR program that pretends to be Windows CHKDSK"
category: cs
tags: [bootloader, evil maid, windows, CHKDSK]
---
{% include JB/setup %}


![nina maluca](http://f.cl.ly/items/1C0G3808241i1D011G0q/nina.jpg)


Have you ever seen a movie where a hot spy lady pretends to be a maid just to discover the villain's secrets? Well, the idea behind an "evil maid" attack is that someone, as the cleaner (aka, maid) sticks a SD card with the bootloader into somebody's PC when nobody's around. After a while she goes back, recover it (with saved login data, passwords et al) and own the machine.

From the github page:

>This is s simple 512-byte MBR program that pretends to be Windows CHKDSK. It asks the user for a password, writes that password back to the media it booted from, renders that media unbootable, and reboots.

`CHKDSK` - "check disk" - is a command on computers running DOS and Windows that displays the file system integrity status of hard disks and floppy disk and can fix logical file system errors. It is similar to the `fsck` command in Unix. An MBR holds the information on how the logical partitions, containing file systems, are organized, since it is a special type of boot sector. For instructions on how to assemble the program - yep, it's a [.asm](http://www.fileinfo.com/extension/asm) file -, install on a disk and extract the saved password @[AlexWebr](https://github.com/AlexWebr/evilmaid_chkdsk)

Wikipedia entry on [bootkits](http://en.wikipedia.org/wiki/Rootkit#Bootkits).