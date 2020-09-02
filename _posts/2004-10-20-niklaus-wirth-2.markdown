---
date: 2004-10-20 20:18:29
layout: post
title: Niklaus Wirth 2
---

The success of Pascal came many years after it was done, due to the availability of microcomputers. Now there were lots of people available to program who didn't have to unlearn Fortran. It was driven forward by Borland making the compiler available for only 50 dollars, when other compilers cost thousands. This made a mass market for Pascal.

Many systems at this point could only be built by teams. A way to partition systems was necessary, and led to the the concept of modules, and the development of Modula. Most people still stck with Pascal. Wirth expected everyone in their right mind to switch from Pascal to Modula, but they didn't.

Started working on Oberon, which was implemented based on object oriented techniques. But it was never recognized as an object oriented language. It didn't cleave to the trends at the time, so it was excluded.

So... This is supposed to be about how he got interested in languages. Does he consider a career spent on programming languages well spent? He has always considered himself a teacher, but he knows he can't teach good design. That takes examples, and is supported by a good language. A complicated syntax and voluminous description is a sign of a poor language. Rules governing the language must be determined apart from the implementation.

Measured on this scale, progress has been made. It was worth the time. Most important now is educating programmers on how to use those tools as best as they can. There is a lot more to do.

The essence of programming languages:

To provide a level of abstraction from details of computers.

To provide a suitable model of computation

To allow mathematical reasoning without recourse to knowledge about the underlying mechanisms

For this we require a concise and precise definition.  Fat manuals are a reliable symptom of failure

Then comes Q and A.

The story of Wirth building a helecopter control system. The trick was to make it disappear. It turned into a cyclic turning process. Taking values from sensors and moving actuators. The whole system is Oberon, only one page of code.

Overloading and templates: Wirth says overloading makes sense and belongs in the basic object oriented toolbox. However he says he has some reservations about the way that most systems implement it, Oberon did it very elegently. Never was able to make good use of templates, but some people might.

Knuth stood up and asked about recursion being missing from the original Pascal spec.  It was true, but it was there by the first implementation.

Question about what languages will people be using in thirty years. Wirth says that most people don't program the way that he used to. Now they pick up bits of code from other places. This leads to bloat. In thirty years there will just be more bloat.

Question about functional programming. He says they are interesting, but not really very useful. All so called functional languages have an assignment hidden somewhere. He thinks that people who are fans of functional languages are actually fans of programming without non-local variables.  The fans say thats really very close to the truth.  And Wirth says that he programs like that himself.
