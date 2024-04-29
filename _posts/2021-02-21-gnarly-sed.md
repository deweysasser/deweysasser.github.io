---
categories:
 - sed
 - shell
---
Last night I wrote a script to compute a Table of Contents for Markdown documents and insert it into
the document. It handles both syntaxes for heading blocks.  (I also wrote a git hook to run this
script on commit.)

It contains what is probably the most gnarly sed script I've ever written. I am *so* glad we've
moved beyond sed.

(However, sed is also everywhere without having to install other tools on almost any system, which
is why I used sed and awk instead of something more modern.)

Anyway, for your reading pleasure (or torture), here it is:

```shell
/^#/ {
        s/^\(#*\) */\1|/
        p
        }
        /^--*/ {
        x
        s/^/##|/
        p
        }
        /^==*/ {
        x
        s/^/#|/
        p
        }
        h
```