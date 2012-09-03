---
layout: post
title: "Halting Problem"
description: "If we have a function stops(x) that takes a program x and returns true if x stops. Then we can make a program like this."
category: cs
tags: [halt, computation, loop]
---
{% include JB/setup %}


If we have a function "stops(x)" that takes a program x and returns true if x stops. Then we can make a program like this:
    
    program p(x):
    while stops(x): continue;
    
This program takes program x and runs for ever if x does not run for ever.
But the value of "stops" depends on what x it is given.
What happens if we run program p on itself? p must work on every possible program, so it must be able to work on program p, so we can say p runs for ever if p does not run for ever.
This is clearly impossible and was used by Alan Turing in 1936 to prove that there is no program that solves the halting problem.
 
As Pullum beautifully put in his SCOOPING THE LOOP SNOOPER (A proof that the Halting Problem is undecidable):

>No general procedure for bug checks succeeds.
>Now, I won’t just assert that, I’ll show where it leads: 
>I will prove that although you might work till you drop, 
>you cannot tell if computation will stop.

 Read the full poem [here](http://www.lel.ed.ac.uk/~gpullum/loopsnoop.html)

 Read the Wikipedia entry [here](http://en.wikipedia.org/wiki/Halting_problem)