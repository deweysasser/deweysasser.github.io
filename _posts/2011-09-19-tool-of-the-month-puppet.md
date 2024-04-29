---
excerpt: Puppet is a tool for configuring a large number of machines by recipe and
  periodically checking that they are still in conformance.  I have fallen in love.
categories:
- tool of the month
title: 'Tool of the Month:  Puppet'
slug: 'tool of month: puppet' 
created: 1316408400
toc: true
---
Ah, [Puppet](http://puppetlabs.com/), how much do I love you right now?

# Summary
In a nutshell, Puppet is 'make' for computers.  

Like make, you specify rules and dependencies and recipes to fulfill rules.  

Puppet has either local (make this computer) modes or client/server modes, and the latter is the most useful.  Communication in client server is secured by SSL certificates and puppet itself implements reasonably good key management.  However, the last documentation I read on the subject pointed out that puppet had not gone through a security audit.

My own current take away is that when I'm using puppet over the wild and woolly Internet (and I do, for remote machines), I configure my firewall to only accept connections from the specific machine.  No, this is not (typically) secure, but between that and the SSL it should be enough.

# Getting Started

I have found Puppet to be very approachable.  Here's my suggestion to starting out:

1) Install Puppet from the ruby source
2) Start playing around with local rules using the "puppet apply" command

This will let you get a feel for puppet on the computer you're currently logged in to.  From there, you can install a puppet server and branch out to multiple machines.

If you have a small installation (I have around 15 machines at home), you can use puppetmasterd.

At work I have a semi-large installation (currently about 400 machines).  I'm using puppet under Apache/Rack.  Currently having those 400 machines fetching puppet configurations of low to moderate complexity every 30 minutes is putting about 25% load on a single-core, 1GB RAM virtual machine.

# Puppet GUI

Puppet labs has a web UI called Puppet Dashboard.  It works reasonably well at home (~10 machines).  It is effectively unusable at work (~400 machines).  Page refreshes take around 60 seconds currently.

There are other web UIs available, but I have yet to use any.  ([Foreman](http://theforeman.org/) looks interesting.)

# My bootstrap pattern

In order to configure machines on Puppet, puppet has to be running.  Puppet requires ruby, so a bootstrap process is, at minimum, to install ruby and puppet.(Foreman allegedly handles the initialization, but I haven't delved into it yet.)

I currently have some SSH scripts to install ruby & puppet on a number of Linux distributions, then run puppet.  I have written puppet recipes to take care of the rest.

My script also handles installation onto OpenSolaris using the [Blastwave](http://www.blastwave.org/) repository for ruby, but installing Puppet from the most recent source.  Again, I have puppet recipes from there on out.

# "With Great Power Comes Great Responsibility"

Yet, as a matter of fact, you can make one mistake and render all of your machines broken at once.  (Not quite at once:  using the default settings it will take 30 minutes to roll out.)  I am planning to implement a phased rollout pattern to take care of this, assuming that Foreman doesn't do so already.

I will update this page when I do so.
