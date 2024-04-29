---
categories:
- git-for-svn
title: The problem with GIT
slug: problem with git 
created: 1335112261
---
After a few months of using GIT, I realized one of my fundamental problems with git:

Commits aren't.

By that I mean that the term "commit" has a connotation in software that is beyond the strict definition.  I think it likely comes from relational databases where "commit" connotes some kind of finality or permanence.

In relational databases or file systems, a "commit" is the point at which you can't undo -- it's been place on persistent media.  They only way to change a value now is a "compensating transaction" -- i.e. roll forward.  You cannot roll back after you commit.

Source control systems such as RCS, CVS and Subversion preserve this semantic.

In git, however, things are much more fluid.  A "commit" has no real sense of permanence.  For git the conceptually irrevocable action is the "push" -- i.e. to publish one's "commits" to someone else.  Even here the "permanence' of that change is advisory rather than mandatory -- it's simply not a good thing to yank the carpet out from under someone using your code.

With git you are *constantly* changing your commits -- any time you do a rebase you are lying about history -- and git shows this by having different signatures for the commits.  Also any cherry-pick.

This is true in subversion (and CVS, Perforce, ...) as well -- a "svn up" is pretty much the same thing as a rebase, but with only a working set of changes in your sandbox you don't have to actually grapple with what you're doing.  A major difference is that since you haven't "committed" you don't (or at least I don't) have such a strong attachment to "this is now a part of history and shall not change".

I'm starting to think of a "commit" as more like an idea than a position -- which would imply that when a group of people use git it is more like a conversation than a mechanistic construction.  This later seems like an interesting idea to explore, but I have code to, um, commit.
