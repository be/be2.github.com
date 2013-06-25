---
layout: post
title: "Lua tables and inheritance"
description: "Lua class-like tables and inheritance"
category: programming
tags: [lua, code, programming, classes, inheritance]
---
{% include JB/setup %}   
    
    
  From the brief "Learn Lua in 15 Minutes" - of course you wont if you don't know already how to program, but still a good tutorial for intermediate to advanced coders on some Lua's programming language fundamental features. I chose to show you the class-like tables and then present an example o inheritance using those. 
  
  In Lua classes aren't built in, so you can build them in different ways. To do that you can use tables and metatables. 
  
  
    Dog = {}                                   
    
    function Dog:new()                         
      newObj = {sound = 'woof'}                
      self.__index = self                      
      return setmetatable(newObj, self)        
    end
    
    function Dog:makeSound()                  
      print('I say ' .. self.sound)
    end
    
    mrDog = Dog:new()                          
    mrDog:makeSound()  -- 'I say woof'         


Although `Dog` looks like a class, it's a table. That's because Lua's only compound data structure; and tables are just associative arrays. A table can have a metatable that gives the table operator-overloadish behavior.

As an inheritance behaviour example we get:

    LoudDog = Dog:new()                           
    
    function LoudDog:makeSound()
      s = self.sound .. ' '                       
      print(s .. s .. s)
    end
    
    seymour = LoudDog:new()                       
    seymour:makeSound()  -- 'woof woof woof'      
    
Nasty dog. 
