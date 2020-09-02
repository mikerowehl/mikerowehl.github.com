---
date: 2005-10-08 03:42:18
layout: post
title: Coroutines (Navel Gazing Warning)
---

[This mention of lightweight cooperative multithreading and coroutines](http://it.slashdot.org/article.pl?sid=05/10/06/2223232&from=rss) caught my eye for some reason. Maybe cause it's been a while since I wrote anything in C and I got a patch this morning for one of my open source palm programs. Which of course got me thinking about programs that write programs, a concept which gets discovered and rediscovered often enough that I think I've seen it about a half dozen times in my relatively short career. Given [the new gig](http://www.ning.com) I've been thinking a lot about domain specific languages, abstraction, and metaprogramming. In particular I've been thinking about the tradeoffs between mature systems that exhibit good abstraction and the cut-and-paste reuse that most people instinctively sneer at. Programming in C actually tends to mix the two styles quite a bit. C code tends to be maleable because of the tools available to shape it, the (often abused) macro facility, and the ability to do just about anything you want with your types if you use pointers. Watching something like the Linux kernel evolve through sets of patches makes you realize that there is a metalanguage in the deltas. Over time interface points in the code shift and join, moving from interfaces used in change sets to interfaces instantiated in the model of the program itself.





So how do you encourage the same maleable programming when you have a bunch of independent programs? Can the same cut-and-paste evolution style that helped grow the web take hold in application code? The coroutines implemented in a bunch of tricky C code are relatively easily represented [in scheme using continuation passing style](http://gd.tuwien.ac.at/languages/scheme/tutorial-dsitaram/t-y-scheme-Z-H-14.html). When do you implement using C and when do you push the function down into the language itself? I'm just wondering in writing at this point, I don't have any answers to this one.
