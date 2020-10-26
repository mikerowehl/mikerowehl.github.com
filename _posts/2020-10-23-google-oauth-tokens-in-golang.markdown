---
layout: post
title: "Google Oauth Tokens in Golang"
date: 2020-10-23 20:26
---
I'm pretty sure I've run into this before and worked through it. But for some
reason my searches didn't land on something that clicked till I was a few
iterations in. So I'm putting down a simple example so that when I search for
it next time I'll find it... hopefully.

This is specifically for building a web app that authenticates against
[Google Sign-In](https://developers.google.com/identity/sign-in/web/sign-in).
The web part of the setup is super simple to get working, and there are tons
of examples and tutorials. Once I got to the phase of sending the token to a
backend service to validate things got a little more rocky. First thing to
note is that the
[key to use when verifying a token](https://developers.google.com/identity/sign-in/web/backend-auth)
is shared across all services. Cause I had mostly been following info in
tutorials I didn't realize that for a while. I was trying to figure out how to
use the info from my project admin UI to validate. It was only after running
across another example of verifying a Google based token that I realized there
was a PEM somewhere that held the verification key.

The info on that page says the Google API Client Libraries are the suggested
way to validate a token. But honestly I can't get the Go version working for
this simple case. I thought I was using the libraries properly, cause they
seemed simple enough to just validate a token. I even found
[a Stackoverflow sample](https://stackoverflow.com/a/62984078/506507)
that was almost exactly the same as what I had done. But I keep getting an
error out of the library that the token is invalid. I actually think there's
some other dependency in that library. The error isn't that the token I'm 
providing is invalid, but that the Google API Client assumes I have some kind
of identity setup (that Stackoverflow answer says to "provide your Google
credentials to your application"). I didn't really want to figure out what
that was all about. And those Google API Client libs are crazy huge in their
Go implementation. When I did a go get on them it downloaded almost a gig of
objects. So I started trying out some alternatives.

There's a
[nice clean JWT library](https://github.com/dgrijalva/jwt-go)
that looks like it's still in pretty regular use. And it does work very well.
It can just be a bit tough to dig up a good RSA based example of validation.
There are some convenience functions in jwt-go that make it pretty simple to
setup. But there are a bunch of examples around that seem to pre-date some of
the convenience functions. So even the good samples can sometimes be a bit 
intimidating.  Plus the tokens that you get back from Google embed a key id
that you need to use to lookup the right certificate from their public
listing. So I put together a sample using a current version of jwt-go:

<script src="https://gist.github.com/mikerowehl/3094498f6227571c736d3662e4cb2ae5.js"></script>

This is just a sample mind you, you don't want to be fetching a chunk of JSON
over http in the key lookup function if you're using this in some middleware.
But the ideas are all there I believe: verify that the signing method is the
expected algorithm, use the key ID from the token header to find the right
verification key, and uses a nice convenience function to parse the PEM from
Google very simply into a form usable as the return from the key lookup.

You should be able to just go run it as a standalone, pass in the token you
want to verify, and you get back the claims from the token if everything
worked. If things don't work definitely use the
[tokeninfo endpoint](https://developers.google.com/identity/sign-in/web/backend-auth)
before you dig in too much. That service can really simplify basic things,
like pulling out the wrong string from a web response to use as a token. Not
that I would every do that, no. But I've heard from friends that they've had
that problem ...
