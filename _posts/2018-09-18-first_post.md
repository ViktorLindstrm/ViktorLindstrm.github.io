---
layout: default
title: "First Post"
date: 2018-09-18
---

## First Post

Hi all, this will be the place where i gather my thoughts and thinking while
programming on an OAuth2 Authorization Server and/or an OpenID Connect Identity
Provider. 

I will fill this blog with my thoughts regarding the specification(s),
programming details and overall thinking of all regarding programming an AS/idP

Some info about my actual project, it is a development because I wanted to get
a better understanding about OAuth2 and OpenID Connect, and the relation
between. The programming is done in Erlang, mainly because i think it is fun to
program, but the scaleability might come in handy later on. The webserver is an
Erlang webserver called ["Cowboy"](https://github.com/ninenines/cowboy). It
fits in the overall flow nicely and is mostly used for the API and the very
minimal webfront to do the login and management.

It is not done, so much is still to do, and alot to write about. But it is a
functioning OAuth2 Authorization Server. That means that it complies (mostly)
with the Specification for one of the flows, Authorization Grant flow. Since 
that is the most interesting for my current setup. More about that in the
future. 

That was a quick intro, and see you again soon. 

