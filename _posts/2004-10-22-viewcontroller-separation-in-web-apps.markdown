---
date: 2004-10-22 10:34:31
layout: post
title: View/Controller Separation in Web Apps
---

A recent article ([Migrating to Page Controllers](http://www.onlamp.com/pub/a/php/2004/10/14/page_controller.html)) does an excellent job of combining theory with some concrete examples and immediate benefits. The article provides a simple technique for factoring the controller out of the view processing when writing PHP code. Although not necessary for everything, architecture along this direction can really pay off for web apps. Many of the PHP apps that I've looked at recently have stand alone pages, and that can make them pretty hard to transform. The trend to move all the processing up to the front of the page helps out quite a bit. Programmers now tend to setup their objects and variables all in one block at the top, and then include the display pages with minimal markup to output the dynamic bits. Unfortunately error display still gets stuck into the logic pretty often. It certainly helps out quite a bit to have all the processing done up front, and that's half way to the page controller model. The final bit is the refactoring to pull the different views out of the logic and defining a consistent scheme for passing the display info to them. I like the way the description comes off, very practical and tailored towards those who have to refactor their apps to make them look like this.






Check out the earlier article, [Building a PHP Front Controller](http://www.onlamp.com/pub/a/php/2004/07/08/front_controller.html), as well. That gives the same kind of treatment to overall application flow. A minimal set of changes to bring about huge benefits. I've seen a few big products aimed at trying to formalize the separation between overall application flow and page processing, and it can certainly be taken to extremes. When it's all said and done, reworking the flow of an application can be complex if you're using a flow engine or if you're using standalone pages with some application and display objects. I was happy to see that the article included a bit of commentary about when to use a front controller and when it might be unnecessary overhead:






> Few techniques are suitable for everyone. If your web site updates involve adding new pages in-flight, then the overhead of the map maintenance may work against you. However, if the dynamic nature of your site depends on something outside of the raw pages (such as a database) or if your changes involve carefully-tested migrations, then the Front Controller technique may benefit you long-term.
