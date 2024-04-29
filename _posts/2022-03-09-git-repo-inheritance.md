---
published: false
slug: did you know that you can "inherit" files from other git repos, and keep them up to date?  Here's how.
categories:
- git
---

# TL;DR

* Git can merge from branches that have unrelated history.  
* Once it's merged, they're no longer unrelated, and you can merge diffs
* You can use this to create a set of common "mix in" files in a central location and then merge updates to other repos.

If you read the above and go "yup, got it", you probably don't need to read more.

Otherwise, read on...

# The Problem

Sometimes you just need some boilerplate files that are the same in multiple repositories, and for tooling reasons (e.g. GitHub Actions) you can't just reference them in a central location.

That's fine, and that's why GitHub has ["template repositories"](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-template-repository), right?

But templates only solve the "start off this way", and doesn't deal with "I need to change this file and update all the places it's used" (i.e. the standard "inheritance" use case)
