---
layout: post
title: "git remove files which have been deleted"
description: "git remove files which have been deleted."
category: code
tags: [git, remove, git rm]
---
{% include JB/setup %}

Curious about how to remove files from git which have been deleted in your local directory? There are a few ways to do it, but these two below are the most ellegant solutions. `cd myproject` to your project directory via terminal and insert the following code: 

    $ git rm $(git ls-files --deleted)

This command handles git rm'ing files that you've deleted.

The other one you can use is:

    $ git add -u

It deletes all removed files, updates what was modified, and adds new files.

Keep in mind that the removal isn't immediate, it will be completed after the next update, aka next `push`.

Code found @commandlinefu.com 

