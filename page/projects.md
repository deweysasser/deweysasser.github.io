---
title: Projects
layout: single
skip-title: true
---

# My Open Source Projects 

(hosted on Github)

## [runbook-framework](/content/runbook-framework)

Implement manual/automatic runbook checklist/scripts.

## [locksmith](https://github.com/deweysasser/locksmith)

Tool to inventory and manage SSH (and other) keys across multiple systems.

## [docker-xymon](https://github.com/deweysasser/docker-xymon)

A package of [Xymon server](https://xymon.sourceforge.io/) in a container. Can run in kubernetes or 
straight docker.

I mostly like Xymon because it's very easy to add network tests, and it's great at hierarchical rollup of status.

## [docker-xymon-client](https://github.com/deweysasser/docker-xymon-client)

Containerize the docker xymon client.  This is suitable to run on every docker note to monitor the node
and report to the above server

## [git-updater](https://github.com/deweysasser/git-updater)

A container to run a `git pull` to mirror files from a repository to another directory.  Good for automatically
deploying software.   Thank *very* abbreviated gitops.

## [docker-restic](https://github.com/deweysasser/docker-restic)

Add bandwidth control to the standard restic container.

## [markdown-doc](/content/markdown-toc)

Generate tables of contents for Markdown files.

## [git-dirsync](https://github.com/deweysasser/git-dirsync)

Use GIT to synchronize directories across multiple machines.