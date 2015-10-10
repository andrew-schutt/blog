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

    "Let me show you the chimes." =~ /chime/

The above code will return the index that the start of the match occurs (in this case 20).  If a match had not been found `` `nil` `` would be returned instead. For the record this is just a glorified `` `.include?` `` and is basically useless since you are likely better off using `` `.include?` ``

    "Where did all of the pie go?" =~ /mouth/ #returns nil

    "Soft blanket and cold night.".include? "night" #returns true

Alright we can make a simple regular expression! Great success! 

# Character Classes

Although we can match the pattern of a string included another string this doesn't offer much.  Lets start taking a look at some of the other pattern matching abilities of regex.

With character classes we are able to define a range that we would like to match.  This is represented with square brackets around the range we are trying to match.

    "Don't eat those magazines." =~ /[quw]/ #returns nil
    "Do I have vowels inside of me?" =~ /[aeiou] #returns index at first match
    
The second example above showcases a great use case for the use of a range.  We are looking for any vowels within the string.  

# Ranges

Next up lets take a look at ranges.  Ranges are sets that can encompass large sets of characters.  All digits for example or the letters of the alphabet.

    "1234567890" =~ /[a-z]/ #returns nil
    
This example is a little understated, but the string contains only digits so no characters between a-z match.

    "ABCDEFGHIJKLMNOPQRSTUVWXYZ" =~ /[a-z]/ #returns nil
    
What do you mean this returns ``` nil ```?!  Well did I mention it is case sensitive?  

    "ABCDEFGHIJKLMNOPQRSTUVWXYZ" =~ /[A-Z]/ #returns index at first match (0)
    
It is also possible to negate a range.

    "1234567890" =~ /[^a-z]/ #returns index at first match (0)
    
So that is how ranges work in a nutshell, but the cool part for ranges is that they have some shorthand syntax as well.

* \w -> [0-9a-zA-Z]
* \d -> [0-9]
* \s -> any whitespace 

* \W -> [^0-9a-zA-Z]
* \D -> [^0-9]
* \S -> anything NOT whitespace

* . -> matches anything not a newline character

# Modifiers

Regular expressions also have the idea of a modifer to give additional shorthand to some of the more lengthy options.

    "Find capitalized Words in a Sentence" =~ /([A-Z])\w+/ #return 0 for first match
    
    "123.123.123.123" =~ /^\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}$/ #returns 0
    
The first example above will find any word that starts with a capilized letter.  The second will identify a correctly formatted ip address.

# Exact Matching

The second example above also makes use of exact matching to ensure that an exact match of the regex is found.  This will strictly enforce the match from the string start to end.

    /^   $/   
    
    
# Conclusion

Welp, that's all for today regarding regular expressions.  For more information be sure to look at the [Ruby documentation](http://www.ruby-doc.org).

