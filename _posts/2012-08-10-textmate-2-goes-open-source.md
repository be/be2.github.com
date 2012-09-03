---
layout: post
title: "Textmate 2 goes open source"
description: "TextMate 2, one of the best text editors for OS X 10.7+, goes open source (GNU General Public License)."
category: apps
tags: [osx, textmate2, open source]
---
{% include JB/setup %}


TextMate 2, one of the best text editors for OS X 10.7+, goes open source (GNU General Public License). To bootstrap the build you need to run:
    
    git clone https://github.com/textmate/textmate.git
    cd textmate
    git submodule update --init
    ./configure && ninja

Assuming that you have already installed XCode and Git, of course. 

You can install the prerequisites via homebrew:

    sudo port install ninja ragel boost multimarkdown mercurial 

For more information visit the Textmate [github page](https://github.com/textmate/textmate). 