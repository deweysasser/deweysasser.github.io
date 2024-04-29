---
categories:

- admin

excerpt: Traefik has changed everything, breaking TLS for this site. I'm not a fan of the
        redesign.
---

Ahhh, the [Second System Effect](https://en.wikipedia.org/wiki/Second-system_effect),
a perennial project killer.

For some years, this site has run in a Kubernetes cluster with several others, and
used [Traefik Proxy](https://traefik.io/traefik/), which has been an excellent piece of code, to
multiplex sites through one load balancer.

For better or worse, my provider has just forced a kubernetes upgrade...which removed some
deprecated APIs...on which traefik 1.7 depended.

And, instead of maintaining the same standard API of reading annotations from standard Ingress
objects, traefik has gone the "custom resource definition" route, destroying the simple and
elegant (and standard!) way of using it in favor of complicated and proprietary ways of specifying
everything.

Of course, it's always possible that Traefik is doing this to contribute to monetizing their
software. My opinion on that is a topic for another day.

I will update this page later with some details, but for now, the result is that TLS on this (and
several other) sites are broken until I can either reconfigure everything to use their new system,
or replace them with other methods.

I apologize for the inconvenience. TLS is very useful, and right now we don't have it. Gagh!