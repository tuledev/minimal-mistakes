---
title: "Highlights for The Pragmatic Programmer-by Andrew Hunt, David Thomas - Part 3"
categories:
  - Books
tags:
  - Books 
  - The Pragmatic Programmer
---

*This is a highlight and summary content for my favorite parts*


## Chapter 4: Pragmatic paranoia

You can't write perfect software

The analogy with coding is pretty obvious. So we are taught to code defensively. If there are any doubt, we validate all information we're given.

## Chapter 5: Bend, or Break

Life doesn't stand still.
In order keep up with today's near-frantic pace of change, we need to write code that as loose - ass flexible - as posible. Otherwise, we may findout code quickly becoming outdated.

### Decoupling and the Law of the Demeter
#### Minimizie coupling
Need to be carefule how many other modules you interact with, and more importantly, how you came to interact with them.

### Metaprogramming

Everytime we have to go in and change the code to accommodate some change in business logic, we run the risk of breaking the system - of introducing a new bug.

So we say "out of the details", get them out of the code. While we're at it, we can make our code highly configurable and "soft"-that is easily adaptable to changes.

#### Dynamic configuration

We want to make our systems highly configutable. Not just things such as texts, colors, but deeply ingranted items such as algorithms, database products, middleware technology,...
> Configure, don't integrate

Use metadata to describe configuration options.

#### Metadata-Driven Application

Our goal is to think declaratively, and create highly dynamic and adaptable programs. 
We do this by adopting a general rule: program for the general cases, and put the specific somewhere else - outside the compiled code base

> Put abstractions in code, details in metadata

Define most details untils the last moment, and leave the details as soft as posible.

## Chapter 6: While you are coding

Avoid programming by coincidence-replying on luck and accidental successes-in favor of programming deliberately

### Program by Coincidence

Doesn't know why the code is failing because didn't know why it worked in the first place.

#### Accidents of Implementation

It's easy to be fooled by this line of thought: "It works now, better leave well enough alone..."

#### Implicit Assumptions

It's easy to assume that X causes Y. DON'T ASSUME it, prove it.

#### How to Program Deliberately
- Always be aware of what you are doing
- Proceed from a plan, whether that plan is in your head, on the back of the cocktail napkin, or on a wall-sized
- Rely on reliable things
- Dont be a salve to history

### Algorithm Speed

There is a kind of estimating that programmers use almost daily: estimating the resources that algorithms use - time, processor, memory, and so on.

It's a good idea to make sure an algorithm really is a bottleneck before investing your precious time trying to improve it.

### Refactoring

> Change and decay in all around I see

As a program evolves, it will become neceessary to rethink earlier decisions and rework portions of the code. The progress is perfectly natural.

### Evil Wizards

Don't use wizard code you don't understand

<br>

---
<br>

* [Highlights for The Pragmatic Programmer-by Andrew Hunt, David Thomas - Part 1](https://tuledev.github.io/books/highlight-the-pragmatic-programmer-part-01/)

* [Highlights for The Pragmatic Programmer-by Andrew Hunt, David Thomas - Part 2](https://tuledev.github.io/books/highlight-the-pragmatic-programmer-part-02/)
