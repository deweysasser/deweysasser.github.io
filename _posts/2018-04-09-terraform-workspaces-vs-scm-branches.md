---
excerpt: "TL;DR:  Workspaces and branches serve different purposes.  An SCM\r\nbranch
  is an alternet set of code.  A Terraform workspace is an\r\nalternate location to
  apply code.\r\n\r\nYou should use the difference to..."
categories: []
title: Terraform Workspaces vs SCM Branches
slug: terraform workspaces vs scm branches 
created: 1523273571
toc: true
---
TL;DR:  Workspaces and branches serve different purposes.  An SCM
branch is an alternet set of code.  A Terraform workspace is an
alternate location to apply code.

### Overview

At first glance, terraform workspaces look like just a poor repeat of
branches in your SCM tool.  So, why do you need them?

Because they're about branching a different thing.

Yes, you could achieve similar results using only SCM branches but
you'd be folding 2 different concepts into the same mechanism, making
keeping track of the result error prone and complicated.

### Assumptions

This thinking assumes that you test (or at least want to test) all
changes in a non-production location (hereafter called a "sandbox").
It assumes that changes are developed and evaluated and only applied
to actual production once the full consequences are understood.

One common practice is to have a special sandbox called "staging" that
is designed to be as much like production as possible and provides a
final verification that changes for production will
work.

### SCM Branches

The purpose of SCM branches are to create an alternate set of source
code.  It appears that each set of source code might correspond to a
target environment, but that's not true for 2 reasons:

1) you might want to develop different features in different SCM branches,
and those features will eventually be applied to the same target
location (or locations).

2) You want application of your production changes to be fully
exercised in a sandbox first.  Using SCM branches for this creates a
greater possibility that the code is different, resulting in surprises
in production.  Effectively, ensuring that code is not
(unintentionally) different in sandbox and production environments
becomes a manual process.

Of course, you need a way of distinguishing your sandbox from your
production, and differences can creep in anyway.

### Terraform Workspaces

Terraform workspaces are branches in the *target* environment.
Functionally, you're using a separate Terraform state file, which can
be shared between several users (or could be entirely separate).
Semantically, you're separating out the location to which the
terraform templates are applied and tested.

Also, I've found it useful to use a different variables file across
different workspaces, to account for differences in e.g. IP blocks or
target DNS zones.

### An example of a practical difference

Here's how things can go, using workspaces and branches for separate
concepts.

NOTE:  in this section I'm using `git` conventions for SCM but the
concepts are equally applicable to other SCM tools.

You have a production branch of code (we'll call this `master` branch).  You
want to make a change, so you make a branch (we'll call this
`feature`).  You develop your changes on `feature` and apply it to the
`sandbox` *workspace*, mutating some infrastructure that is local to
your development effort.

At this point you have changes in branch `feature` that have been
validated in a private `sandbox` deployment.

When you're happy with how things are working out in the `sandbox` branch
area, you commit (or merge) your code to the `master` branch.  It is
now queued for production.

You then change to the 'staging' *workspace* and apply your `master`
branch to make changes.  You can observe the behaviors in staging to
both verify that it does what you want and verify how it will impact
your production services availability.

`Staging` differs from the previous develop sandbox in that it is, as
much as possible, a clean duplicate of production (without any cruft
caused by testing multiple development attempts, and perhaps with a
more production like set of data).

Changes applied in `staging` are a good predictor for how they will
work in `production`.

At this point you have changes in branch `master` that have been
validated in a private `staging` *workspace* (e.g. a deployment).
You're about to apply the exact same changes to your `production`
*workspace*.  You know they're the same because they're produced by
the *exact* same code (of course, conditionals based on different
variables can produce different results.  It behooves you to minimize
conditionals for this reason.)

At this point you can (if necessary) schedule maintenance and apply
your `master` branch to your `production` *workspace*, which
presumably makes the changes available to end users.

