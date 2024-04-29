---
categories:
- git-for-svn
title: 'GIT for SVN users:  A simple Github workflow with multiple repositories'
slug: git-svn-users-simple-github-workflow-multiple-repositories 
created: 1404920626
---
This is one article in my [series](http://deweysasser.com/tags/git-svn) on GIT for SVN users. See [the introduction](http://deweysasser.com/content/git-svn-users-introduction).

One of the inherent assumptions in the SVN world is "the" repository.  "The" repository is the place from where you check out, from where you update, to where you commit.

GIT does have a strong concept of "the" repository but it's used very differently:  it's the repository you create every time you make a workspace.  You know your .svn directory?  Well, the .git directory isn't just a cache and state-tracking device (as in SVN) -- it's an entire repository with all version history.  Yes, I know you know that, but it has interesting consequences.

What if you could very easily synchronize SVN repositories with each other?  Think "svnsync" but with fully bidirectional sync possibilities?  That's what GIT can do -- easily and mostly transparently.

In GIT, you can have *multiple* copy/sync locations (called "remotes" or "remote repositories").  GIT handles this well -- you can checkout from one repository, update from a 2nd, merge code from a 3rd (which may or may not have everything the first has), then commit to a 4th remote repository.

In GIT, "the" repository is always there, always local (almost -- but never mind that for now) and entirely yours.  All the things people call "repositories" out on the net (e.g. github) are copies.

So, in GIT, the only thing which warrants the label of "the" repository is...the repository you create every time you make a sandbox workspace, and it's all yours.

Are we confused yet?

Let's explore some consequences:

First consequence:  it is possible and often even desirable to be able to completely edit commit history, *as long as you haven't published it to others*.  That emphasized section is the killer, though, and it's managed in GIT mostly by convention (i.e. "don't do that -- it hurts").  Unfortunately, it doesn't hurt you but hurts the people who are trying to collaborate with you.  Do this often or without good reason and people will...stop collaborating with you.

The result is:  [a commit isn't](http://deweysasser.com/content/problem-git) (until it's shared with someone).

2nd consequence:  We can (and likely should) have multiple remote repositories with different contents.

GIT has 2 primitives:  "push" and "fetch", which respectively sync your local (sandbox) repository to and from other repositories (*NOT* pull -- that's a bit different, and yes, I know it's poorly named).  There is (by default) an overridable safety to make sure you don't clobber someone else's changes with your own.  Overriding that safety is a big gun -- make sure no one's foot is in the way before pulling that trigger.  (It's also possible for someone who owns a target repository to prevent you from overriding this safety.)

By the way -- GIT has a name for a semi-special remote repository called "origin".  In reality, "origin" isn't special at all, it's simply the repository you used to create your current one and git creates the link for you.

OK, so lets put this all together in an example.

Let's say I find a very nifty project on github that *almost* does what I want.  I want to use it after I hack on it a bit.

     git clone https://github.com/example/nifty

Poof -- I now have *copied* the entire nifty repository locally.  I'm left with a remote named "origin" which is cool but currently useless.

     # hack hack hack,
     git commit -m "Made even more nifty changes -- it now solves my problem perfectly" -a
     #  debug, hack hack, debug, hack
     git commit -m "OK, now it actually works and really solves the problem" -a

Excellent!  We're good to go, except

* Your local area is the only place where these changes are in SCM (you have backups right?  Yeah, that's what I thought.)
* You're not sharing this with *anyone*.

So, what we should really do, to be good OSS doobies, is ask the original maintainer to merge in our changes (or at least publish our changes for others who want even more nifty code).

Of course, the original maintainer is *NOT* going to give us commit access to their repository.  There's no reason for them to do so.  ("Committer access" was such a badge of prestige in the old world.  Alas.)

So, back we go to github to make a "fork" of the origin project.  In GIT, forks *are not* bad -- they're the normal way of doing things.  (See what I mean about non-obvious consequences of GIT?  In CVS and SVN, fork == bad == a split in the version history that will require heroic effort to heal.  In GIT, no biggie, dude, it's just a branch.)

OK, now we have a repo on github that has exactly what the origin contained (which has, of course, changed since we originally cloned because other people are hacking nifty, too).

So, *first* we want to merge the upstream nifty changes into our stuff, then we want to publish our changes, *then* we can ask the maintainer to use our changes.

Copy all new changes from the origin repository to our local repository

     git fetch origin 

Merges the origin changes into our code -- oh, look, the original "git clone" effectively created a private branch.  Merge conflicts are tangent to the discussion at this point.

     git merge origin/master 

(Remember the badly named "pull"?  It does both of these steps in one shot.  I consider it "badly named" because it is *not* simply the opposite of "push".)

OK, now our local repository is completely up to date with the maintainer *and* has our nifty changes, but how the heck do we publish it, particularly as we want to check out to a *different* place that we cloned?

Recall that git allows multiple remotes.  We just need to add one and then use it, so...

     git remote add mine git://github.com/MINE/nifty.git

Now we have a 2nd remote named "mine" (and yes, we still have "origin") but we've done nothing with it as of yet.  Let's publish our changes

     git push mine master

And now we have published our changes to *our* copy of the nifty project.

To get our changes back to the maintainer, we need to create a "pull request" on github (but that is another tale).

NOTE:  None of this has done anything with GIT branches in either local or remote repositories.  When you "clone" you are effectively making a private local branch.  That's enough for now.
