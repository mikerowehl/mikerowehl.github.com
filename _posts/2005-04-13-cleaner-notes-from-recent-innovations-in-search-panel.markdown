---
date: 2005-04-13 11:38:50
layout: post
title: Cleaner Notes from Recent Innovations in Search Panel
---

I posted [raw notes](http://www.bitsplitter.net/blog/?p=485) yesterday for this event, here's the cleaned up version.  The event was ["Recent Innovations in Search and Other Ways of Finding Information"](http://www.baychi.org/calendar/20050412b/). There's going to be audio of the event posted, I'm not sure if it's going to be to the [BayCHI site](http://www.baychi.org/) or somewhere else. The panel started with a 5 minute show and tell by each panelist, they had slides or walked through the tools they're working on.

Panelists




  * Peter Norvig


  * Ken Norton


  * Mark Fletcher


  * Udi Manber


  * Jakob Nielsen



Peter Norvig

Talked about the newly released question and answer feature on Google, where you can ask a question in natural language and get a direct answer back. The example he gave was "what is population of japan". The facts for the database are extracted from the web overall, using statistical analysis because most facts tend to be represented multiple times.  Accuracy is still a problem however.

He then spoke about search by SMS.  They're seeing more and more demand for mobile services.  They've added maps to the cell phone interface as well.  The Google maps interface has recently grown the ability to switch to a satellite view mode.  He showed satellite views within google maps of a few interesting landmarks like Niagra Falls and the white horse in new mexico.

Then Google suggest, where the searchbox suggestion list is populated behind the scenes by google as you type.  In particular he referenced the [AJAX model](http://www.adaptivepath.com/publications/essays/archives/000385.php) (hat tip to Jesse James Garrett) that Google has been pushing.  Used in both maps and the suggest feature.  Then an example of Google desktop search, indexing local files and information for users and mixing it into search results.  Showed an example of a search combining results from out on the web and on the users own machine.

Ken Norton

First slide said "Enable people to find, use, share and expand all human knowledge".  Most people working on search are only adressing that first part, how to help people find information.  Yahoo wants to be involved in all parts of that series. Reference to remixing and remaking (author note: alla [Lessig's remix culture](http://www.oreillynet.com/pub/a/policy/2005/02/24/lessig.html)).  Then showed a big list of projects that Yahoo has in beta or released. Desktop search, creative commons search, the search API (YDN), mobile search, whole bunch of stuff that went by too quick to capture all of them.

Talked in particular about MyYahooSearch, which is in beta but will be released soon. The service will give users more control over their searches, allowing them to save and share.  Like bookmarking, but hopefully a step beyond with respect to sharing and enhancing.  Video search is up now. That's something they wouldn't have considered 3 years ago because there wasn't enough content. Now the content and the demand is there. He mentioned [MediaRSS](http://tools.search.yahoo.com/mrss/) as the way to share your content back out after remixing it.  They also have a desktop search.

Y!Q is an effort to "bring search back to the point of inspiration".  Every search happens for a reason, it starts at a place where someone realizes there's something they want more info about.  That context is potentially valuable info. What kind of context should be captured and how should it be given to the engine?  How is the information represented to the user? The example given was reading a court decision and looking for related stories in the news. The interface shown was a floating popup with the news links appearing over the court decision page.

Mobile search is also big with them, users are demanding multiple access modes.  Creative Commons search was also driven by customer demand, users were asking for content that they could reuse in their own work. Also referenced the Yahoo purchase of Flickr, a photosharing and community site. The hope is to integrate the DNA from Flickr with repect to understanding of how users tag and share and expand on content and cary that throughout Yahoo.

What's next at Yahoo? Personal search, contextual search, multimedia search, desktop search, local search, travel search, social media. Check out [next.yahoo.com](http://next.yahoo.com).

Mark Fletcher

Mark did a walkthrough of Bloglines to show the functions. The tool is divided up into four areas: search, subscribe, share, publish.  That should provide the full lifecycle of blogging that people would want. He started Bloglines to scratch his own itch, he had bookmarks for a hundred sites he had to visit every day. Talked about information overload, blog content is the fastest growing area of web content. 1.6 million articles added every day.

Sidenote: Mark has 29 feeds in his own account (at least the one he demoed with) Showed how to use the search built into Bloglines.  It's a keyword search you can do across all content or across feeds you're subscribed to. If you hit the save button you can subscribe to the query, and it'll cull out new occurances of the keywords in articles and feed them to you.  The example of a search feed he has is a keyword search for "Bloglines" within his aggregators folder.

What's coming from Bloglines? Search friends, filter articles.

Udi Manber

Udi spoke about the [Yellow Pages](http://www.amazon.com/gp/browse.html/104-6832396-8708716?node=3999141), which launched in January. It includes a function that lets you walk down the street virtually. When you click left and right you can see pictures taken at regular intervals.  He did a quick demo of the function and everyone was amazed (gasps and "oooh, ahhh").  Very obvious that everyone was impressed.  He gave an example of why you would want a function like that.  If you gave directions to a place by saying "It's this place right next to that place on main street" that used to mean that you couldn't find the information you wanted online. Now you can find "that place on main" and just walk next door to see what it's called, and complete your search.

He gave some details about how they actually went about putting the site together.  Showed the rental SUV with the camera on top that took the pictures. The camera is hooked up to a laptop with GPS and some special software that tells them were they've been already and shows them were images have been taken.  The driver just looks at the map onscreen and drives, the system does pretty much everything else.  Udi himself spent two days driving the route in Arizona, it was a lot of fun.  Showed a video of the time the intern who had to drive Washington DC was stopped by the police.  The police asked him "is there any tape in the camera", to which he replied no, cause the thing records straight to hard drive.  The police didn't think about that though, so now there's a half hour video of the police talking to the intern.  This holds a good lesson for search, you have to ask the right questions.

Jakob Nielsen

Started off with a table showing that since 1994 we have almost a 100% change in usage. People used to use one word in searches in 1994, and they use on average 2 words in 2004.  This is probably a continuing growth curve, up to a point.  We probably will see three search terms in a few years.  Probably won't ever make it up to something like ten terms, should plateau somewhere in there. People will never use complex queries and boolean operators in large numbers.

How many people are successful in their searches? 42% for all searches.  That divides up into about 32% success rate for inexperienced users and 50% for the experienced user.  When using internal search on a website it's about 33%, and when it's one of the big external search engines it's 56%.

Says that search on websites is a miserable failure.  It's a deisgrace that we've allowed search on websites to be so bad, and intranets are even worse. It's the most prevalent problem actually.

He then showed a video of a recorded session of someone trying to search. The search interface being used was AOL.  There were multiple fields on the page and the user first entered their search text into the wrong field but pushed the search button.  They got no results.  So they clicked the search button a few more times on the results page, still getting no results.  Next stop is the help function, which isn't that helpful.  She enters something like "www.head.ache.com" into the location bar for the next attempt.  The site isn't found, but the browser has a search box on the error page.  She presses the search button without entering any text, but the browser tells her that's an error and that she should type text in the box. She's thrown for a bit by the modal dialog box telling her that she must enter text, but eventually she dismisses it, enters a search, and gets a results page.

---------  Now questions from the moderator

First question is to ask the other pannelists to reply to "search on websites is a miserable failure" statement that Jakob made.

Udi - Says that it's not a failure, 50% is good.  It's a hard problem.  In the example given it was AOL search, who have massive resources to put behind making their search good. When you have a small site and very small resource pool to pull from how can you hope to fulfill well?  The small sites just can't do it, it's not plug and play enough and standardized.

Mark - There's a lot of work to be done, but it's not just search. In the movie that Jakob showed the user was having basic issues, like using the mouse and understanding the layout of the browser. Computers overall have to be more usable, not just the search interfaces that they present.

Peter - The same thing happened to him with the IBM site when he was looking means something.

Ken - More and more people are using the general internet search with site restricts to do their search.  Before you do it on your own, think about using one of the existing engines out there instead.

QUESTION - How have searchers (people performing searches) evolved besides simply using more words in their queries?

Ken - Demand for better search tools in vertical areas.  People used to be happy with general queries in the search engine, now they want the context to be appropriate to their task.  Yahoo is looking at the different categories that users seearch in and trying to figure out what goes in those different areas.  How do you make the user aware of it once you have it.  The results page is a poor place to message to users about features and functionality. 

Peter - Verticals also, very important. International also really stands out for Google.  Majority of traffic is outside of US and not in English.

Mark - I'm the new guy at Ask, so here's what others told me they're seeing: the query length at Ask Jeeves is getting shorter actually, oposite of what most others are seeing. This is because people realize it's not JUST natural language at Ask, you can enter keyword searches as well.  The long tail has grown even longer.  Vast major part of queries are completely unique. Expectations have grown, searches are successful, people search more, feedback loop.

Udi - The size of the search box actually influences the length of the search terms.  Also thinks vertical is important.  Opensearch, syndicated search for opening search and sharing it.  Anybody can take search results and put it on A9.

Jakob - People use search because they are selfish, because they don't want to endure the interfaces that most sites inflict on them.  That applies to both site specific searches and general search engines. If sites did use more standard and humane design (site maps, richer navigation) that might not be the case.  It has to be standard design though, not a one off trick for each site.

QUESTION - How do you give access to the different verticals without turning into a portal?

Ken - The web search box IS the interface.  That's what people want.  Don't direct people to different areas, just figure out the context and provide them with it in place.  Rather than asking users to adapt ask the search engine to be smarter.  Is this a local query? Is this a shopping query? Find the users intent.  Users have gotten confident.  That used to be the greatest problem, but it's not the case any more.  They expect good results.

Udi - Some queries work well and others don't.  "What's the population of India" works even without any natural language processing because it's an objective question.  "What's the best TV to buy" does not because of that term "best".  How do we balance ease of use and powerful tools?

Peter - We've failed in terms of letting the user have a dialog.  Search is a command line without a documented interface.  How do we put advice in place to help guide users to what they want?  We're getting there but it's nothing like walking into a library and getting help from the librarian.

*** Someone on the panel asked how many people in the audience have read advanced help for any search engine. Lots had. That's atypical, in the average group not many have, if any at all.

QUESTION - Are folksonomy/tagging a fundamentally different form of data than what's there already for search?

Udi - It's all just metadata, it's our job to deal with it.  It's not any different, except that hopefully its coming from more sources.

Ken - It's remarkable in that it's just like what we already deal with.  Right now all the information we have is provided by web authors, and now with tagging we can collect from a larger group of people.  The more metadata the better.  The more we can get from users and not authors the better off we should be.

Jakob - We won't get much more info from users. With tagging the barrier is lower, but it's still there. We have to get passive data out of people, eyeball time and metrics from the desktop.

Ken - If they find value they'll do it.

Jakob - Okay, like spam marking in collaborative filter.

Udi - Mapr maps Flickr images onto a map display.  Lots of the images appear in Maine, cause people tag with "me" (as in myself), but Mapr thinks it's an abbreviation for the state Maine.

-------

There are questions from the audience now.  These are just the cool bits I particularly liked.

Udi - A9 keeps context.  If you repeat a search 4 months after the initial date at which you performed it you'll get a message that says "these results are new, you haven't seen them before" and you'll be presented with the information that's been added to the index since the last time you searched. And "these are the items you clicked on last time you searched" so that you know what you've already hit.

Someone from the audience asked under what circumstances the panel didn't use search.  I really liked the answer from Jakob.

Jakob - People do not search when they're loyal customers of someone.  If you're a loyal customer of Amazon you don't search for books on Google, you go directly to Amazon to make your purchase.

Someone asked if the search wars were going to be defined in terms of branding and not tech. All seemed to think it was still a tech race. In that regard the industry is still evolving. There have been times in the past when the search war was thought to be over, but something always comes up and changes the game. The same is true now, there's plenty of evolution to go.

Tags: [BayCHI](http://www.bitsplitter.net/tag.php/baychi) [search](http://www.bitsplitter.net/tag.php/search)
