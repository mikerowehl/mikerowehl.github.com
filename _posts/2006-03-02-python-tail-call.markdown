---
comments: true
date: 2006-03-02 13:50:19
layout: post
slug: python-tail-call
title: Python Tail Call
wordpress_id: 626
categories:
- General
---

This is pretty interesting, a [tail call optimization decorator for Python](http://aspn.activestate.com/ASPN/Cookbook/Python/Recipe/474088). It doesn't work for a lot of cases.. like these ones:


> 

>     
>     @tail_call_optimized
>     def even( n ):
>       if n == 0:
>         return True
>       else:
>         return odd( n - 1 )
>     
>     @tail_call_optimized
>     def odd( n ):
>       if n == 0:
>         return False
>       else:
>         return even( n - 1 )
>     
>     @tail_call_optimized
>     def countto( n ):
>       if n == 0:
>         return 0
>       else:
>         return 1 + countto( n - 1 )
>     
>     print odd( 31 )
>     print countto( 31 )
> 
> 





It forced me to actually take a look at decorators in Python to figure out what was going on and why they failed though. The basic flow of the "throw an exception and catch it at a higher level" idea is easy to follow. However what it's doing when it catches that exception at a higher level is pulling the input arguments up to the higher level and reevaluating with the new arg set, and I'm not even sure what exactly it's doing in the case of mutual recursion, and seems to stick to only one of the functions.




[This one works for mutually recursive calls](http://lambda-the-ultimate.org/node/1331#comment-15165), but I haven't dug into it yet. Looks interesting though. However it doesn't work when the return value feeds back into the recusion:




> 

>     
>     @trampolined
>     def countto( n ):
>       if n == 0:
>         return 0
>       else:
>         return 1 + countto( n - 1 )
>     
>     print countto( 3030 )
>     




The stack overflows when I try that. The scheme implementations don't have a problem with it however:




> #;1> (define countto (lambda (x) (if (= x 0) 0 (+ 1 (countto (- x 1))))))
>     #;2> (countto 30000)
>     30000
>     
> 
> 





Still, interesting stuff to dig at.
