---
excerpt: Description of a successfully implemented, fairly light-weight SCRUM process.
categories: []
title: Feeling Scrummy?
slug: feeling scrummy? 
created: 1522035127
toc: true
---
This was originally written for an infrastructure engineering team.
The team was split between systems engineering tasks and operaitons
responsibilities.

We successfully implemented this SCRUM process and, in conjunction
with some accountability/build process changes, substantially improved
our work quality and predictability.

# Feeling Scrummy? 

## TL;DR

* Stories have the user, goal, motivation and acceptance criteria, or
  we don't start them
* Sprint planning turns stories into tasks.  We work on tasks, not
  stories.  Finding new tasks after planning is not goodness.
* We never work on something that's not a task.y
* We reserve 20% of our time for "unplanned work" (break/fix tasks)
* Tasks have success criteria and a max duration of 8 hours (you can
  split into 2)

There's a lot in here that will seem uncomfortable a first.  It's
motivated by making a predictable, manageable process.  Management is
important.  Deal.

## Contents

* Motivation and Intention
* What we get out of it
* A note on process
  * Work Processes: Time boxing and success criteria
  * Responsibilities
    * The Team
    * The Backlog Owner
    * The Scrum Master
    * Management
* How we get it
  * Stories and Task and "Done", Oh My!
    * Stories
    *  Tasks
    * Done and "Done Done"
  * Some notes on scheduling
* Our Process
  * Sprints (time boxed)
  * Daily Standups (time boxed) & Discussions (criteria based)
  * Estimation Meetings (time boxed)
  * Sprint Planning (criteria based)
  * Sprint retrospective (time boxed)
  * Sprint review (time boxed)



## Motivation and Intention

We need to change our process.  We've been operating in something that
resembles semi-controlled chaos dressed in scrum clothes.  (OK,
perhaps a bit better than that.  Still...)

I believe it will be better for all stakeholders (us, our peer groups
in the company, our managers who are measured on what we get done, and
ultimately the people who pay us) to improve our progress by adding
more scrummish rigor (rigor-scrumtis?) to our process.

We need 3 things from a development process:

* productivity
* predictability
* transparency

We need to add manageability to our process, so this document lays out
a series of conditions that we will agree we MUST meet.  Also, we MUST
meet them in spirit as well as letter.  This is not to say that we
can't do other things and that we can't deal with exceptions, but that
we're going to be doing this *for real* and not just for appearances.

I'm not going to get into the basics of scrum.  I'm going to describe
how we should make it work here.  If something doesn't make sense,
please Google until it does (or come back and say "Dewey, you're an
idiot and here's why" and we can have a productive conversation about
it).

What I'm describing here is *NOT* the fullest, most complete Scrum
process it's possible to do.  I'm describing the simplest things that
must be done to have a successful process instead of having success
despite a process.

## What we get out of it

When we have predictable velocity, it makes it easy for the backlog
owner to manage our backlog and future work, show the rest of the
company that we're valuable, and know when we need to add capacity to
the team.

When we're working on tasks, it makes it easy to for managers to tell
what we're doing and where we are and have confidence that we're going
to get things done.

## A note on process

### Work Processes:  Time boxing and success criteria
All processes in scrum are either

* time boxed (meaning you spent a fixed amount of time and you get
what you get)

* criteria driven (meaning you're not done until it's met success
criteria done).

It's important to understand the difference and *stick to it*.
If we find something that's time boxed that consistently doesn't have
enough time, we change the *process*, not push the envelope in
individual tasks or meetings.

One frustration with time-boxed meetings is that you often don't get
to everything.  That's not a bug, that's a feature.  It prevents
"beating a dead horse".  If something is important, it's going to come
up at the next time-boxed meeting anyway so there's no worry.  It
enable and enforces prioritization.

### Responsibilities

#### The Team

The scrum team owns the tasks.  This means that the team is
responsible for getting them done as they've committed.

In scrum, management does *NOT* tell a team what they must do, only
what must be done first.  The team commits to getting things done.

As this is fundamentally foreign to the way people reflexively manage,
there is a cost to this, which is: commitments MUST be met.

The *TEAM* commits, not individuals.  There is no "My stuff is done,
you suck".

The team owns estimates, but the backlog owner has to make sure the
team has good data on which to estimate.  The backlog owner owns the
priorities, but the team must give good estimates so the backlog owner
can prioritize.

#### The Backlog Owner

The backlog owner, um, owns the backlog.
Ownership means that she gets to decide what's on it and in what order
-- deciding what is important to do.  (The team has *input* but not
ownership.)

The backlog owner owns backlog quality, but the team is responsible
for doing the best estimates it can on the basis of the known data
(which *will* change over time).

#### The Scrum Master

The scrum master is responsible for making sure we scrum correctly and
keeping track of all of the various items.  (This is not an enviable
job.  This can be "herding cats" at it's finest.  Buy her flowers
and/or booze.)

#### Management

In a well running scrum process, managers do very little day to day.
What is traditionally software "management" is actually backlog
management and task assignement.

In a SCRUM process, management is about creating a productive
environemnt and getting blockers out of the way that's beyond tam
scope.  Basically, everything around getting things done": staffing,
facilities, etc.


## How we get it

### Stories and Task and "Done", Oh My!

#### Stories

The purpose of a story is to understand the target so you can aim
properly.  Ultimately, a story consists of the 5 Ws (and you thought
writing had no place in STEM).

The critical parts are:

* A "Role" (or a "User"):  this describes the perspective to address.
* A goal:  what the user is trying to accomplish.
* A motivation:  Why they are trying to achieve this goal

I find it's also a *great* idea to explicitly and separately state
success criteria (also called "Acceptance Criteria".

Before we can start on a story (i.e. before it can be accepted for
work during a sprint) it must have all 4 of these.  Yes, sometimes
they're obvious.  Great, that means they'll be easy to write.

I don't care if it's the whole, stilted, formal "As a Driver, I want
my car to go faster when I press the accelerator" or just a set of
key/value pairs.

We'll estimate stories in "Story Points" with the goal of measuring
our velocity.  "Story Points" allow the backlog owner to tell other
people (management, other teams), roughly when we'll complete things.
Story points are an artificial measurement that isn't tied directly to
time -- the velocity is measured.

####  Tasks

Notice that you can't actually do a story!  Stories are not
actionable.  In order to enable a story, we must break it into tasks
("install accelerator petal", "connect petal to throttle", etc).

"Sprint Planning" does 2 things:

* You figure out how much you're going to do in a sprint 
* You decide what tasks are necessary to implement a story (if you
 haven't already).  Also, you estimate these tasks.

Stories also have success criteria.  (Otherwise, how do you know when you're done?)

Tasks are estimated in hours.  Like story points, we'll have a task
velocity, but unlike story points our goal is to achieve a 1:1
(average) correlation with real time.

Note that it's possible to have a time boxed task for exploratory
work.  If so, *stick to the time box.*

#### Done and "Done Done"

Really, truely done -- I mean "Done" done -- means 2 things:

* You've achieved your success criteria
* Your User can execute their story.

This last is the hard part.  How do you know it's possible?

Hint: the best way is to actually *watch* a real user do it.

Until a real user has done it, you don't know that you're actually
done.  The best you can say is "I believe it will work but I can't
know that until we get it in front of the user."

### Some notes on scheduling

You don't plan to work nights and weekends.  If you do that, you're
being a hero and getting more done.  This is great.  It's also not
sustainable, you'll burn out, and your velocity will suffer later.
It's sometimes necessary to achieve short term goals.  It's always has
a price from the future.  Interest compounds.

## Our Process

### Sprints (time boxed)

We'll use 2 week sprints (what we're doing now).  I suggest we
start/end on Wednesdays to stay away from the weekend and minimize the
impact of holidays/long weekends/etc on our processes.

We'll measure velocity in "Story Points per Week" in case we want to
change the size of the box down the road.


### Daily Standups (time boxed) & Discussions (criteria based)

Once we have actual tasks, the daily stand ups will turn into "what
I've just done, any changes, and what I'm doing next".  All discussion
should be deferred until post-standup (often called "parking lot
items")

Separating status from discussion makes for much cleaner, more
understandable meetings and allows people who are uninterested in
parts of the discussion to leave.

We should time-box our status to 15 minutes max.  Discussions can then
take time as appropriate, because they are *contributing to the tasks
we're doing*.  Discussions are done when they're done.

### Estimation Meetings (time boxed)

Estimate upcoming (post-current-sprint) stories in story points.  Top
of the backlog is most important, working down.  If anything changes
(up to the point where it's accepted into the current sprint), we
re-estimate.

### Sprint Planning (criteria based)

If a story does not have the 4 required parts, it can't be planned.
If we can't break it into a series of doable tasks, it can't be
planned.

Sprint planning turns stories into tasks and commits to achieving a
set number of success criteria. If we're playing pool, this means
we're calling our shots.

Sprint planning ends when

* We are willing to commit to a set of stories for the upcoming sprint
* All of the committed stories are broken up into tasks of no more
  than 8 hours


### Sprint retrospective (time boxed)

Yup, I'm sneaking this one in because we're not going to do it for
about 3 sprints.  This is the place where *improvements* happen -- we
take a look back and the sprint and figure out what worked and what
didn't and make things better.

We'll start this around late August and it will take significant time
for about the next 4 sprints, then will stabilize out.

### Sprint review (time boxed)

Present what we did.  We'll keep this one off the radar until we
decide we need it.

