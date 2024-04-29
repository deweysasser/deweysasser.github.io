---
categories:
- git-for-svn
title: 'GIT for SVN users:  An introduction'
slug: 'git-svn-users-introduction' 
created: 1404920507
---
This is part of a series of posts about GIT for people with an SVN background.  If you're an experienced GIT user, my series of ["GIT for SVN users"](tags/git-svn)  is likely not going to be useful (other [GIT](/tags/git) articles might be -- you'll have to make that call).

What makes this different from the bazillion other ["GIT for SVN"](https://www.google.com/search?q=git+for+svn) articles on the net?  Well, this is a place where I can link when someone asks me "how do I use GIT"?  More importantly, I'm going to try to write about GIT from the perspective of a knowledgeable SVN user looking forward to GIT, not a knowledgeable GIT user looking back at SVN.  I'm going to try to do this before my view of SVN is completely subsumed into my "SCM in general" thoughts (which has already started to happen).  There are usage patterns and other things in GIT that are very much *NOT* obvious to an SVN user, even after reading a description of the difference.

My own SCM progression has been RCS->RCSFRONT->CVS->SVN->GIT, with a smattering of Perforce, ClearCase and (Gods help me!) Visual Source Safe (ugh -- I've tried to suppress that memory).

Moving from SVN to GIT was the first time I had to do a mental model change.  However, once I made the change I found that my SCM world *completely* opened up.  There are things you don't do commonly in SVN because the work of the plumbing outweighs the (typical) benefit.  There are things you simply *can't* do in SVN that GIT handles easily and that turn out to be very useful.  Like many paradigm changes, it's not at all obvious why all this is good until you've made the shift, but after making the shift you simply can't go back without feeling like you're hobbled.

If you're doing work with GIT (or SVN), I have written some utilities that you might find useful:

* [https://github.com/dmsasser/gittools](https://github.com/dmsasser/gittools)
* [https://github.com/dmsasser/svntools](https://github.com/dmsasser/svntools)  (amongst others, this contains a tool called "svn-mergebench" which makes SVN merges behave much more like GIT).

I'll be tagging all of my GIT-for-SVN articles so you can find them easily and keep them separate from my pure-GIT articles.
