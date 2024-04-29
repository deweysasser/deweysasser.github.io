---
categories: []
title: Thoughts on running software
slug: thoughts on running software 
created: 1418151789
---
I'm partially on operations guy, so, net result, I'm responsible making software run.  What exactly does this mean?

Here's the minimum set:

* RUN:  Arrange for it to run
* MONITOR:  How do I find out if it stops running?
* PUBLISH:  Make it available to the people who need it
* ADVERTISE:  And make sure those people know about it.

Other things I might want to do depend on the quality of job I want to do (a.k.a. "Service Level Agreement" or SLA)

* Durable:  ensure it keeps running after maintenance and transient problems (i.e. survive a reboot, recovers from a network outage, etc.)
* Repeatable:  Make it something I can easily set up again.
* Recoverable:  If something goes wrong, make sure I can get it back to where it was (this implies backup strategy)
* Resilient:  "DR" -- be able to keep providing services in the event of critical failures.

These lists are in rough order of importance (but sometimes things vary).

In the desktop world, the first part was mostly "slap it on a CD and they'll tell you if it stops working" coupled with "how do we sell this thing?".  In a SaaS environment this is somewhat different:  monitoring becomes more important (for large scale services, no one is going to call support but they'll get on social media and tell people it's not working).  Also, the "it depends" aspects start becoming interesting.  For any significant service, durability and resiliency become important.  Repeatability becomes important for upgrades and development.  

A lot of people believe that if it's resilient it doesn't need to be recoverable.  Perhaps true, perhaps not -- I've easily lost an order of magnitude more data to user mistakes than I have to systems failures, so even resilient systems might need to be recoverable.

Ultimately, what you do with each pieces depends on your requirements, but it's worth considering all of them.
