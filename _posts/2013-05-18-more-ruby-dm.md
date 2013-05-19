---
layout: post
title: "more ruby dm"
description: "More examples of De Morgan laws in ruby"
category: programming
tags: [ruby, logic, De Morgan]
---
{% include JB/setup %}   
    
    
    
More examples of De Morgan laws in ruby, for the sake of entertainment, aka 'just for the lulz', nothing really practical.

In a software that just runs on unix or linux environments:
    
    if !unix? && !linux?
      terminate
    end
    
or
    
    unless unix? || linux?
      terminate
    end
    
If you write a program to monitor your vpn service's logs keeping (the good ones never keep their logs) and price measurement:    
    
    if !cheap || !nologs?
      cancel_vpn
    end
    
or
    
    unless cheap? && nologs?
      cancel_vpn
    end
    
And an example that takes a classic unix [sdf](http://sdf.org) command as an argument - `mkhomepg` - which creates a homepage on your own free shell account (sdf members can't run ruby under ssh, only ARPA members can run ruby, for more info type `arpa` when logged in).  
    
    if !validate? && !donate?
      no_mkhomepg
    end
    
or
    
    unless validate? || donate?
      no_mkhomepg
    end
    
    
That's it, folks.
    
    
    