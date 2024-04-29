---
categories: 
 - gcp
title: 'Google Next:  Networking'
slug: 'google next: networking' 
created: 1532625234
---
Google thinks about networking in a way that is truly revolutionary.

Instead of their network models having physical representation it appears to be more like a compiler:  a process assembles the networking implementation and pushes it as far down the stack as possible.

The result is that there is very little in the data path and so it’s very low latency.  They can also easily change implementations.  E.g. AWS took 2+ years of “its almost done” for cross region VPC peering but Google appears to have rolled out VPC sharing (ability to create your own instances attached to someone else’s VPC) in 6ish months.

The result is that their current network and organizational models are much better for the reality of large scale deployments.

No, this isn’t really surprising but it’s still amazing.
