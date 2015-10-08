---
layout: post
title: "Regular Expressions With Ruby"
date: 2015-07-09 23:46:50 -0500
comments: true
categories: 
---

Good old regular expressions.  Something that you can use to solve a plethora of random programming problems you will come across.  With regular expressions it is becomes possible to simplify many complex problems for searching text.  I have countless times created complex loops searching a string for certain text that in the end could be solved with a regular expression.  

But what all is a regular expression?  And how can you unlock the power regular expressions give you?  Lets take a look.

# Getting Started

First and foremost what does a simple regular expression look like?  Here is a basic example.  Lets open our handy IRB console and give this a whirl.

```
"Let me show you the chimes." =~ /chime/

```

The above code will return the index that the start of the match occurs (in this case 20).  If a match had not been found `` `nil` `` would be returned instead. For the record this is just a glorified `` `.include?` `` and is basically useless.

```
"Where did all of the pie go?" =~ /mouth/ #returns nil

"Soft blanket and cold night.".include? "night" #returns true

```

