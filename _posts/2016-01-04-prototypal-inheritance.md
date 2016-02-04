---
layout: post
title:  "an attempt at understanding prototypal inheritance, part 1"
date:   2017-01-04 0:00:00 -0500
categories: prototypal inheritance javascript
---
### Introduction

As part of my winter break homework at General Assembly DC, I've been tasked with writing a blog as a 'tutorial-for-past-me'. For this, I thought it'd be interesting to explore this topic in object-oriented Javascript, especially since numerous sources have emphasized how critical this is to understanding JS.

### Setting the Stage

What is object-oriented programming and why is it an important paradigm?

>An object is a self-contained entity that consists of both data and procedures to manipulate that data.

In a nutshell, object-oriented programming lets us model data as nouns, their properties as adjectives, and their associated behaviors as verbs. While other programming paradigms [exist](http://people.cs.aau.dk/~normark/prog3-03/html/notes/paradigms_themes-paradigm-overview-section.html), OOP is an intuitive way for us as programmers to structure our code in a way that models real world objects.

### Classical Inheritance

In Ruby (and many other OOP languages), an object is defined as an instance of a class.

    class Person
      def initialize (name, age)
        @name = name
        @age = age
      end
      def introduce
        puts "Hi, I'm #{@name}, and I'm #{@age} years old!"
      end
    end

Often, we make the analogy that the class is like a blueprint for which objects are constructed, or instantiated from. In the above example, we define a class `Person` that takes an argument `name` upon instantiation and has a class method `introduce`. Thus, when we create a new instance of that class:

    ash = Person.new("Ash", 10)
    ash.introduce # "Hi, I'm Ash, and I'm 10 years old!"

### Aside: What's the big deal?

Since discovering that this topic has been discussed contention for quite some time, reading up on this subject has been fairly confusing starting from (what seems to be) the middle, with a most posts and blogs in defense of Javascript - leaving me to wonder, what's the problem with classical inheritance anyway?

As far as I can tell, there's nothing wrong. Classical inheritance is well-understood and useful for particular domains. Prototypal inheritance does have the advantages of being more flexible, but has its own drawbacks.

### Prototypal Inheritance
