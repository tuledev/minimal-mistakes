---
title: "Highlights for The Pragmatic Programmer-by Andrew Hunt, David Thomas - Part 2"
categories:
  - Books
tags:
  - Books 
  - The Pragmatic Programmer
  - 02-2019
---

*This is a highlight and summary content for my favorite parts*


## Chapter 2: A Pragmatic Approach

### The evils of duplication

As programmers, we collect, organize, maintain, harness knowledge. Unfortunately, knowledge isn't stable. It changes-often rapidly. It means we spend a large part of time in maintenance mode.
Programmers are constantly in maintenance mode day by day.

DRY: Eeach piece of knowledge must have a single, umambiguous, authoritative representation within a system

#### How does duplication arise?
- **Imposed duplication**: Developers feel they have no choice-the enviroments seems to require duplication
- **Inadvertent duplication**: Developers don't realize that they are duplicating information
- **Impatient duplication: Developers get lazy and duplicate because it seems easire**
- **Interdevelop duplication**: Many peole on a team(or orther teams) duplicate a peace of information

### Orthogonality

Two or more things are orthogonal if changes in one do not effect any of the others.

Eliminate effects between unreleated things

#### Gain productivity
- Changes are localized
- Promotes reuse
- Gain productivity when you combine orthogonal components
#### Reduce risk
- Diseased sections are isolated
- The resulting system is less fragile
- Be better tested
- Tighly tied to a particular vendor 

#### Coding
Everytime you write code you run the risk of reducing the orthogonality of your application

Maintain orthogonality:
- Kepp your code decoupled
- Avoid global data
- Avoid similar functions

## Chapter 3: The Basic Tools
Every craftsman starts his or her journey with a basic set of good-quality tools 
Each tool will have its own personality and quirks, and will need its own special handling.
Each must be sharpened in a unique way or held just so. 


Many programmers make the mistake of adopting a single power tool, such as a particular integrated development environment, and never leave its cozy interface. This really is a mistake.

### The power of plain text
As programmers, our base material isn't woord or iron, it's knowledge.
And we believe the best format for storing knowledge is plain text.
#### What is plain text?
Plain text is made up of printable characters in a format that can be read and understood directly by people.
You can do everything with plain text that you could do with some binary format, including versioning.
Plain text tend to be higher level than a straight binary encoding, which usually derived directly from implementation.

#### Drawbacks

There are 2 major drawbacks to using plain text: 
- It may take more space to store than a compressed binary format
- It may be computatioanlly more expensive to interpret and process a plain text file

#### The power of text
- Insurance againts obsolesence
- Leverage
- Easier testing


### Shell game

GUI interfaces are wonderful. But if you do all your work using GUI, you are missing out on the capabilities of your environment. You won't be able to automate common tasks, or use the full power of the tools available to you.


A benifit of the GUI is WYSIWYG-What you see is what you get. The disadvantage of the GUI is WYSIAYG-What you see is all you get.

The shell is your friend.

### Debugging
> SELECT isn't broken

It is a painful thing. To look at your own trouble and know that you yourself and no one else has made it.

#### Psychology of debugging

Embrace the fact that debugging is just a problem solving, and attack it as such.

It doesn't master whatever the bug is your fault or someone else's. It is still your problem.

Fix the problem, not the blame.

#### A debugging mindset

The first rule of the debugging: Don't Panic

Before starting debugging, turn off many of the defenses you use each day to protect your ego, turn out any project pressures you maybe under, and get yourself comfortable

If your first reaction on witness a bug or seeing a report is "that's impossible", you are plainly wrong. Don't waste a single neuron on the train of thought that begins with "but that can't happen" because quite clearly it can and has.


#### Where to start

Make sure you are working on code that compiled cleanly - without warnings. Set compiler warning level as high as possible. It doesn't make sense to waste time trying to find the problem that compiler could find. We need to concentrate on the harder problem at hand.

Unfortunately, bug reporting isn't an exact science. It's easy to be misled by coincidences, and you can't affort to waste time debugging coincidences. First, need to be accurate in your observations.

#### Debugging strategies

Once you think you know what is going on, it's time to find out what the program thinks is going on.

- Visualize your data: get a good look at the data it is operation on
- Tracing: watch the state of the program over time.
- Rubber ducking: explain it to someone else
- Process of elimination: **SELECT isn't broken**

[Highlights for The Pragmatic Programmer-by Andrew Hunt, David Thomas - Part 1](https://tuledev.github.io/books/highlight-the-pragmatic-programmer-part-01/)

*Highlights for The Pragmatic Programmer-by Andrew Hunt, David Thomas - Part 3*
