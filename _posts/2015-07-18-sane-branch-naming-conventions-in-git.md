---
categories: []
title: Sane branch naming conventions in GIT
slug: sane branch naming conventions in git 
created: 1437238873
toc: true
---
# The Problem:  The state of the branch

I need to be able to glance over a repo and determine exactly what is ready to go and what it does.

I work on a lot of different projects, and will leave a project in an intermediate state for a long time.  I also, alas, have projects for which I'm managing multiple release streams.  There isn't just a "next" release, there is a "next release on the 5.4 branch", "next release on the 5.5 branch", etc.  

There are any number of articles out there discussing branch naming conventions, whether to fork or push branches to shared repo (I have a mild preference for forking), but I haven't run across much which reflects branch *state*.

# My solution:  A "state" prefix

I'm a fan of the "/" separator, and I use whole words rather than 2 ch abs wn nmg.  (in reviewing this post, even I have a hard time understanding that last part).  Basically, with tab-completion and quick cut-n-paste, saving characters is not nearly as important as reducing cognitive load.  I use a prefix to show intention, e.g.:
   * feature/ -- for features/improvements
   * bugfix/ -- for bug fixes

Something I've recently found useful is when I'm "done" with development on a branch, I'll rename it to "ready/<whatever-it-was>".  Why don't I just merge it?  Well, I *do*, you see, but sometimes a branch developed for one release stream will be needed in another release stream...

Also, when I'm creating a pull request, it gives me a place to push my work-in-progress as I'm developing that does *note* update the PR (which someone might come along and decide to merge).  Effectively, when you create a PR, you're *publishing* a branch.  I maintain my "working" branch and "published" branch separately.

# The overall branch naming convention

So, here it is:
<pre>
    BRANCHNAME :: [STATE '/' ]? PURPOSE '/' [ISSUEREF '-']? DESCRIPTION
    STATE :: 'ready' | 'deprecated' | 'saved' | 'archived'
    PURPOSE :: 'bugfix' | 'feature' | 'refactor' | 'experiment' 
    ISSUEREF :: <some string related to the issue id, such as "ABC-123" or "Issue-3">
    DESCRIPTION :: <2-5 words, hyphen separated, which are semantically meaningful>
</pre>

# Branch Lifetime

Branches start out without STATE and perhaps with a different PURPOSE.  When the state or purpose changes, they are either renamed or cloned to a branch name with the proper state.

For example, if I'm going to fix Issue #7 about the login screen, that will go on 'bugfix/issue-7-login-screen-badness'.  When I think I'm done I'll perform a 

    git branch ready/bugfix/issue-7-login-screen-badness bugfix/issue-7-login-screen-badness

Yes, that makes a copy.  Copies are easy to deal with ('git branch --merged').  

If I'm working in a collaborative environment I might push to that name, then create a PR on the "ready/..." variation.  I'll incorporate feedback into my working branch, then push again to the "ready/..." branch when I'm happy.

Branches are merged with "--no-ff" in GIT (I don't work in SVN much any more). 

When I'm fairly sure that a branch will need no further changes or to be merged to anywhere, I *delete the branch*  (yup -- gone!).  As I merge with --no-ff, if I need it back I can always recreate it based on the output of "git log".
After a branch has been merged and I'm highly confident 

# Supporting tools

Here's what I have right now (note that I'll probably be adding some specialty aliases to deal with state in the near future): 

* alias.pending=!git branch --no-merged | egrep '^ *(bugfix|feature)'
* alias.all-pending=!git branch --all --no-merged | egrep '(bugfix|feature)'
* alias.not-pending=!git branch --merged | egrep '^ *(bugfix|feature)'
* alias.done=!git branch --merged | egrep "(feature|bugfix)/"
* alias.current-branch=!git rev-parse --abbrev-ref HEAD
