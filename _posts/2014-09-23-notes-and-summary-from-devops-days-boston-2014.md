---
excerpt: "These are my notes from DevOps Days Boston in 2014.  See the section entitled
  \"Dewey's Summary\" for, well, just that.  The rest is pretty much raw notes.\r\n\r\nI'm
  not expecting this page to be generally useful to the public but want to share it
  with some specific people.  If it is generally useful, bonus!"
categories: []
title: Notes and Summary from DevOps Days Boston 2014
slug: notes summary from devops days boston 2014 
created: 1411466400
toc: true
---
# Executive Summary

DevOps Days was 2 days divided into 2 parts each: mornings were programmed talks and afternoons were dynamically determined breakout sessions.

It's clear that DevOps is heavily Linux biased. There are places successfully doing Windows Devops. Ironically, despite Microsoft sponsoring the event by hosting it at the Microsoft Nerd Center in Cambridge, they did not have anyone presenting.

The program and links to talks and slides are at: [http://devopsdays.org/events/2014-boston/program/](http://devopsdays.org/events/2014-boston/program/)

Attached are my notes from the sessions. Look for the sections styled as

Dewey's Summary

for a brief idea of my takeaways. Look for the lines in **BOLD** for particularly interesting thoughts or tools.

I believe the best tools to investigate were given in

- Tools
- Immutable servers. 

The best overall culture concepts were in

- Metrics Driven Development - DaveJosephson
- 

The best "culture change" ideas were in

- Driving change, 
- Leadership lessons from the Marines
- Metrics Driven Development - DaveJosephson

Questions are welcome! Please emails me questions or start a discussion.

# Talks, Day 1    

## [The Value of Feedback - JohnRyding](http://devopsdays.org/events/2014-boston/program/#talk2)

Dewey's summary: John is clearly working in a young company with fairly low experience developers. I think his solutions are good for that environment, but I don't think they necessarily apply to a more experienced group.

John presented his experience of DevOps at his company, focusing on feedback and collaboration **.**

Long feedback loops are a problem in devops cultures because it does not encourage collaboration.

**They added automation testers to code review team**

Code reviews are usually a good way to collaborate. Sometimes there are holy wars.

Long branch bad code causes problems. Sometimes the code merge is refused and it strains the relationship between reviewer and developer.

Change: do code review starting at the beginning. Add PR [pull request] when the branch is made. [Q: I wonder how much time they spend in code review?]

UX Dailies -- demo of active work. Rule is work demoed is between 25% & 75% done. (Range is solid idea to still actively working.)

**Suggests leading devops adoptions with collaboration and feedback.**



[Interesting thought: continuous code review.]

## [Our long road to self service cloud management & deployment - KevinAmorin](http://devopsdays.org/events/2014-boston/program/#talk3)

Dewey's Summary: Overall a fairly straight forward process, though they've taken it further than we have. 

No walls between ops and dev.

Do Value stream analysis. Identify the bottleneck. Hard to figure out the long term goal.

**Every once in a while look for symptoms and cause. Usually more than a technical problem.**

Mostly a walkthrough of setting up the obvious at his company (SCM, build, AWS)

Use knife-ec2 to describe infrastructure

Understanding state/in use of each system.

Product: Atlas

**Devops messaging: pitch a message and try to change thinking**

## [Infrastructure Testing: Grey Matter - AnthonySpring](http://devopsdays.org/events/2014-boston/program/#talk4)

Dewey's summary: Their particular environment involves managing a lot of servers that they do not control. They write ServerSpec scripts to verify these servers are suitable for use.

We have tools for provisioning and tools for monitoring. Between we have "gray matter"



**Tool: ServerSpec – used to verify servers match requirements**

**Tools: Packer, racker, vagrant, docker,**

# Micro talks

These were 3 minute presentations on various topics:

### Driving change

Dewey's summary: a good approach to introducing devops.

- start small

- build prototypes (let the code talk)

- market the results

- use videos to make presentations

- mentor early adopters

- know your audience (some people don't care about how Facebook ships code)

- be the visionary

- award people for their small achievements

- don't break windows -- it takes a lot of effort



### Maximize terminal information density

Dewey's summary: A discussion of some specific Linux tools for productivity. This was much better for entry level sysadmin than seasoned engineers.

- tmux (the new screen)

- multitail

### Shipbuilding and failed software projects

Dewey's summary: a very interesting talk about changing too much and lessons learned. No specific tools or techniques presented.

Using construction of the Vasa as a metaphor for devops projects.

### Leadership lessons from the Marines

Dewey's summary: This guy was clearly a Marine. I'm not sure it's a good way to run projects in general because not everyone has been to Paris Island, but there are definitely some things they do well.

- job first, then people

- reward your people

- **run disaster drills. You cannot have a highly functioning team without drills**

- details matter

- Clear and concise communication. Say it once well even if it takes longer

- **encourage initiative**

- **understand commander's intent** (context of the instructions)

- failure is a team event

### Chef

Dewey's summary: Chef has nothing special, yet. They're partnering with MS and might be interesting, or might turn more MS –specific on Windows.

They're partnering with MS on DFC.

# Breakout Sessions, Day 1

### Immutable servers

Dewey's summary: a giant round-table on the pros and cons of using "immutable server" patterns, what "immutable" was, where to use it and not use it. 

**Make the bad way inconvenient**

Interesting tools:

Hiroku database

Pgpool to manage multimaster

Pulp repository management

MESOS for bare metal installation.

Tools: vagrant, docker, packer, zookeeper, meals

Interesting ideas:

Use tripwire to make sure nothing changes

### Windows Devops Tools

Dewey's Summary: A small round-table on specific tools that are used on Windows for DevOps. People have been successful buying into the (evidently very expensive) MS stack. There are other tools. Chocolaty seems like a good idea, as does Puppet for Windows. Chef is getting a lot of mindshare but it seems more because it fits a lot of developers than because it's a better tool. It allows people to write Ruby programs to configure machines. It's not so good at infrastructure "convergence".

Microsoft System center configuration management

Team foundation server (TFS) for scm and build

**Tool: Octopus deploy (good recommendation from one person)**

**Tool: Boxstarter**

**Tool: Chocolaty (yum for windows)**

Puppet for windows

- can unattended install sqlserver under puppet

- puppet in windows works reasonably well

**Vagrant runs on windows**

**Allegedly chef on windows does something but isn't great**

MS DSC

InRelease for installation (unbelievably expensive)

**Stack exchange is all .net. They have online docs of their infrastructure [review their docus/blog entries]**

BladeLogic works but it's expensive

**SyatemCenter not good for servers -- not scalable. It's good for desktops.**

(Sensu)

One fellow advocated that DevOps on Windows is just a skill set issue.

This fellow spent 24 person months on puppet, then went to chef (because they got people with that skill set) (interesting fellow -- Christopher Parker, Albany NY)

Full ESX host is $35k incl licensing. Said "ESX Servers are cheap".

**Ancestry.com is a big windows chef shop. They have talks on YouTube.**

# Talks, Day 2

## [The Power of Conflict - NikolasKatsimpras](http://devopsdays.org/events/2014-boston/program/#talk5)

[Dewey's](http://devopsdays.org/events/2014-boston/program/#talk5) Summary: Excellent talk. Review the slides – there was way too much content for good notes. Review the slides and perhaps the video.

There is a cultural transition pandemic of cross functional collaboration

Difference between constructive vs destructive conflict.

However, conflict is friction between people that produces something new. We need more productive conflict. Avoids groupthink.

For most people the rest a gap between what they do and what they think they do. 

**Cognitive biases** :

Anchoring

Fundamental

Attribution error

Selective perception (confirmation bias)

Halo effect

Memory bias

Hindsight bias

Perceptual bias

Duplex perception (McGurk effect)

**Adapt strategy to needs** (presenter showed a graph of power vs cooperative style)

...

**Dev tends to promote new ideas, ops is conservative** .

**Devops is not a hard skills problem, its a soft skills problem**



**Feedback loop mapping**

Foster an environment that favors marginalized voices

## [Intro to CoreOS: Get Ahead of The Curve, New Ways to Deploy and Manage Applications at Scale - KelseyHightower](http://devopsdays.org/events/2014-boston/program/#talk6)

Dewey's Summary: This is a specific Linux platform for minimal platform issues that supports some containers (e.g. Docker)

Have a better relationship with your infrastructure

Self healing

Systemd, cloud-init, update-engine (from chrome), docker, etcd, fleet

Self healing

Fleet allows you to forget about hostnames. Fleet manages scheduling across multiple machines.

Tool: Etcd uses a semaphore to manage who is allowed to reboot. Make sure you don't reboot all of your hosts at once.

Coreos support stand alone exes and docker containers

Going for order 100k nodes with order seconds conversion

[Very interesting tool for managing large sets of machines]

Coreos scheduling probably not good for large databases

None of this live migrates. "It's not VMware"

## [Metrics Driven Development - DaveJosephson](http://devopsdays.org/events/2014-boston/program/#talk7)

Dewey's summary: 2 interesting things here: 1) is chatops culture, which works well for them.

**The more interesting aspect is writing metrics and \*assertions about metrics\* as part of the development process. They view metrics as part of the programming contract, embed them in the code, effectively create monitors at \*development\* time.**

"Chatops" -- use of chatbots for status. Most interesting operations happens in chatrooms.

They use google hangouts as a war room

**Correlating metrics to aperiodic events. Heavily metric based troubleshooting** . Pretty much all discussions about what's going wrong are exchanges of hard data.

**Monitoring isn't a thing any more. It's part of the development process.**

**They're writing pre and post conditions for all services and track those as metrics.**

**"Interesting metrics prove system hypotheses"**

Do this as part of the development process up front. "We're committed to considering the operational requirements of our code up front."

**Instrumentation is NOT debugging.**

Must use the metric system to drive monitoring because monitoring must alert on the same things.

Librato has a blog about this

[http://blog.librato.com/posts/2014/7/16/metrics-driven-development](http://blog.librato.com/posts/2014/7/16/metrics-driven-development)

## [Running Graphite at Scale - AndrewKenney](http://devopsdays.org/events/2014-boston/program/#talk8)

Dewey's summary: Running graphite at this scale requires special deployments and modification of graphite. Their scale is 2-3 orders of magnitude greater than ours.

Flypaper dashboard

Grafana

25 graphite servers globally, 650k metrics

event horizon to put system metrics in graphite.

Cassandra as back end for graphite instead of Whisper

They have devops and ops. Devops is building the tools and is 3rd or 4th level support

# Breakout Sessions, Day 2

## Jenkins ephemeral builds

Dewey's summary: The interesting idea is to not care about state on a Jenkins Master – all build pipelines are described in a domain-specific language and generated into the Jenkins Master. Thus, they can run multiple masters, spin up and throw away build masters, etc.

Jenkins starts as the wild west but becomes mission critical and unmanageable.

What can we do to source control build pipelines.

Using artifactory to store artifacts.

They don't promote, they just complete a pipeline or not. If not, the build is broken.

Allows Jenkins server for each team. Jenkins servers are no longer mission critical. Jenkins servers can be burned down and recreated easily – all interesting state is in Artifactory or SCM.

[Assumptions: build slave configuration is well defined and build slaves are elastic. Artifacts are not stored in Jenkins. May require a pipeline model instead of a promotion model, or that may be an artifact of artifactory]

## The Devops Echo chamber: do we spend too much time listening to ourselves?

Dewey's Summary: A conclusive Maybe.

Tools: Rundeck, sensu

## Config tool throwdown (Chef vs. Puppet vs. Salt vs Ansible)

Dewey's Summary: Puppet and Chef are both capable tools and the choice depends on how you think about your infrastructure. It seems most people moving from Puppet to Chef do so because they have Ruby developers who don't want to learn the Puppet DSL.

Puppet, chef good for end state. Ansible is good for orchestration.

Chef has better local testing/dev frameworks. Test kitchen.

There is a similar tool for puppet. 

There is a puppet provisioner for test kitchen.

[https://github.com/aspring](https://github.com/aspring)

