---
layout: post
title: Gradual AI Transition
date: 2026-06-21 09:38 -0700
---
The use of AI across the company I'm working with is very uneven. There are
some folks who use it constantly every day, and there are plenty of folks who
I'm pretty sure have never even given it a serious try. I'm in the former
group. I had to hop in and get up to speed pretty quickly while not
being able to call on my team all that much. Everyone was underwater and
didn't really have the time to help onboard someone. So I just picked up the
tools I had access to - Claude, code repos, and some command line tools - and
figured out how to make things work. For that use case the AI assistance was
completely amazing. I would not have been able to get up to speed and make
contributions as quickly as I did if I didn't have some AI tooling to help
with that.

It's an enabler however, it's not magic. The other part of me being able to
use those tools to get going is that I have 35 years of practical experience
and knowledge to wrap around the use of those tools. When the AI came back
with answers I was pretty sure were incorrect I had the intuition to dig in
and validate what I was just told. And I had the general understanding needed
to structure some kind of test or cross validation to dig out the actual
correct answer relatively quickly.

Most people picking up the tools aren't
going to have the same background that I do, so I don't assume they're going
to immediately see the same results that I do. I've been spending some mental
cycles recently trying to figure out how they could. Not at a whole
industry-wide
level, there are lots of people who have been working on that issue for
years already. But I'm talking specifically in my role as a devops engineer at
SmithRx, how can I make AI more useful to more of the technical team? How do
we start moving a large org, working in a highly regulated environment and
dealing with stringent member privacy requirements, toward adopting AI? And
how do we do it when many of the engineers have had some kind of negative
engagement with the tools already?

I understand a lot of the push back I hear from some of the team. I
don't want to work on a crappy system full of hastily cobbled together slop
either. And if you just toss a simple prompt at a tool without enough
instruction to constrain the solution, it's still very possible to get
garbage back. Anyone who's worked with the current tools for a while has
probably experienced the crazy behavior where you ask something like Claude to
fix some tests for you, and it just changes the expected values in the test to
whatever happens to be coming out of the unit. They're not magically perfect
tools. But they are high leverage tools. And what we've been doing for a while
now, particularly on the devops side, is figure out how to make our tools more
reliable and predictable.

For me the current challenge of wrapping AI into
the process feels pretty much in line with where we were already headed. This
particular set of tools happens to have a massive scope. But the goals are the
same. How do we make it easy for people to start using the tool? How do
we put some guardrails in so that people can feel comfortable adopting it
initially? Do they have enough leeway to experiment and iterate as they pick
it up? And how do we make a system that gets more resilient and durable the
more the common paths are used?

The macro level answer is the obvious one for anyone already using some AI, we
need to get the context right. We need to have good instructions and
documentation going into AI tools so that they're more likely to do things that
line up with existing code. It should understand the conventions and
design patterns we've chosen across the whole org without having to dig those
details out of the code already there. It should understand how the non-code
parts of the system impact the code - what regulatory requirements might be in
effect for given chunks of code, how does our monitoring and observability
work, what are the processes in our on-call runbooks?

For a large organization that's been around for 10 years, that's a lot to try
to pull together. It's the kind of stuff I track down (and I'm sure others do
as well) to feed into a session when I have a big chunk of work. And I pay
particular attention when it's a chunk of work that spans a few different
systems. But it can take a good amount of effort just to track down the right
info. It would be great to have the right context everywhere, for every repo
to have actual up-to-date agent info. Or even just updated docs that would
serve as a good starting point. That's not what I'm facing though. It would be
a good size project just to try to pull that info together.

I know plenty of people who have done this for their projects, and many of
them are seeing tremendous returns. But in general they picked up AI much
earlier in their project. They were able to build it in from the start. There
are plenty of large existing companies leaning in heavily to building with AI.
But those efforts don't seem to be without issue. When even the forefront
engineering groups like AWS have to walk back their AI stance a bit and start
doing reviews, it reinforces my take that maybe just yoloing it all in on AI
and burning the boats also probably isn't the right stance.

I've been looking for places where we can more gradually ease in to using AI
tools. Places where the changes are less critical path, and hopefully
somewhere that devs are happy to get some extra leverage and spend less of
their time. This weekend at our company hackathon I think I found it. We were
working on a project to help clean up some of the unit tests in our core code
repository. There are tons of tests in that repo, and somewhere along the line
the tests got wrapped in a retry handler. So by default the PR and CI runs can
end up swallowing some info about what tests actually failed. It shows up on
Codecov reports, but it can be hard to track down an actual run to do some
debugging. So we built a simple tool to parse through the logs and find places
where a test failed, to make it easy to go in and fix it.

Built into the tool now is a copyable prompt to drop into an agent to start
working on a fix. Which my AI people immediately point out is a horribly
inefficient way to do things. "Just give it directly to Claude and let it
start working on a fix! Why make a person copy and paste it?"
My hope of course is that we can get the
combination of the prompt we generate from info about the failed test, and the
agent directions in the repo, good enough that we can just let the system
start working on fixes automatically. But I would like to have the rest of the
technical organization involved in working with the system and deciding when
we have something that's ready for that. I don't want to tell them what we
have to do, I want to show them what we can do - and hope a good number of
people follow along.

It's a form of bottom-up adoption of
AI. I see lots of places trying to force everyone to use AI whether they want
to or not. And I think that's part of why it isn't always going very well. It
really should be going well, and I think it can,
if people see a system that solves a real and constrained problem to
start with. If they see something that gets rid of a tedious part of their job
they would like to do
less of, they'll be much happier to pick it up. And happier to spread it to
more places as they get comfortable with it. That matches up with a few of the
success stories I've heard so far. Hopefully I picked a repeatable part of the
pattern. Time will tell. I would love to chat with folks who have done this
before though, especially in larger or longer running technical orgs.
