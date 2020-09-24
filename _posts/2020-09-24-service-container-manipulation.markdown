---
layout: post
title: "Service Container Manipulation"
date: 2020-09-24 16:39
---
The Github actions functionality has been pretty spectacular, in particular
[service containers](https://docs.github.com/en/actions/guides/about-service-containers)
for setting up a test environment. One bit of annoyance though can be trying
to do setup on a container. When the container gets created the
repo hasn't been checked out yet. So I can't do the normal mount of some init
into a postgres container like I would using docker-compose locally. There are
lots of ways to work around that, but I just ran across an example that uses
docker on the runner image and info from 
[the job context](https://docs.github.com/en/actions/reference/context-and-expression-syntax-for-github-actions#job-context)
to exec a few tasks on a service container.

<script src="https://gist.github.com/mikerowehl/187a0a8685079ef5c8c1bd6bf71797a4.js"></script>

Mind blown. For some reason I thought those service containers were tucked
away somewhere special and not exposed directly on the runner system. What a
fantastic tool to have available.
