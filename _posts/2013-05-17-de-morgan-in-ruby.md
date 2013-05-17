---
layout: post
title: "De Morgan in Ruby"
description: "De Morgan's laws of first order logic applied to ruby programming language"
category: logic
tags: [De Morgan, logic, ruby, programming]
---
{% include JB/setup %}



Once upon a time a philosophy undergrad student  entertained, naively, that she'd never ever stand before a symbolic notation or artificial language again. Besides getting scared the shit out of logic classes, she generally had this awful habit of asking questions such like: "professor, will I ever use that in *real life*?". This very kind of question is wrong in so many levels of abstraction that the whole scenario used to be quite baffling, actually; but put aside the nescience of the matter, I always tried to show a few... let's call them... 'real life examples' :P - oh lord. 

De Morgan Laws are transformation rules that are valid rules of inference. They allow the expression of conjunctions and disjunctions purely in terms of each other via negation.

Expressed as theorems of propositional logic we get:

![tpl](https://dl.dropboxusercontent.com/u/5666518/1st.jpg)


Its substitution form is expressed as:

![subst](https://dl.dropboxusercontent.com/u/5666518/2nd.jpg)

using the metalogical symbol of logical proof replacement, we now can express the general RULES:

![rules](https://dl.dropboxusercontent.com/u/5666518/3rd.jpg)
 

'Very fine', very well mr. hell, we all learned that in  undergrad school, maybe even earlier for some. What we don't usually get to know is that many programming languages make heavy usage of De Morgan's laws (by 'we' I mean philosophers, not the  folks of compsci and math, not them). I'll sketch only a couple of examples, only a couple because after two you'll get it and all that'd come afterwards could bring down boredom to deadly levels.  One example is a bulletin board, the other a post office. Ruby is the language of choice, since it is quite clean and easy catching, imho. 

Well my dear friend, take a look at the RULES and now comtemplate the zen of ruby:

    !(a && b) == (!a || !b)
    !(a || b) == (!a && !b)

The examples above I got from the excelent blog about programming called [The Pug Automatic](http://thepugautomatic.com/2012/09/de-morgans-laws-in-programming/), but I'm sure after contemplating the beauty of ruby's code you'll be able to create at least a few more.

###In a bulletin board:###

    if !funny? && !cute?
      destroy
    end

the equivalent, applying De Morgan's lawz

    unless funny? || cute?
      destroy
    end

###In a (rough) post office system:###

    if !big? || !heavy?
      send_as_letter
    end

the equivalent, applying De Morgan's lawz

    unless big? && heavy?
      send_as_letter
    end


Arrivederci!


