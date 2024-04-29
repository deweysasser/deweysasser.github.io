---
excerpt: "A list of guidelines for good DevOps, presented in the spirit of [Shuhari](https://en.wikipedia.org/wiki/Shuhari)\r\n\r\nWrite
  your success criteria first. That way you know when you're done.  If you can't write
  it down then you don't really know what you're doing.\r\n\r\nMake a computer do
  the work.\r\n..."
categories: []
title: Guidelines for Modern DevOps
slug: guidelines for modern devops 
created: 1521021600
toc: true
---
### Start at the end

Write your success criteria first. That way you know when you're done.  If you can't write it down then you don't really know what you're doing.

### Make a computer do the work.

Humans should make decisions.  Computers should make them happen.

Getting this backwards leads to sadness. (Maybe AI will flip this some day.)

### Automate 3 things:  things that happen frequently, things that happen rarely, and things that you really don't want to mess up.

What should you not automate?  Thinking.

### Don't start with perfect

"Perfect" means you don't know enough about it to see the flaws.  You can always see more to do.

### What is the simplest thing that could possibly work?

Less is often more.  It should be as simple as possible, but no simpler.

### If everything is top priority, nothing is prioritized

Priority isn't about what's important, priority is about what do I do first.  Dividing tasks into high, medium, low works approximately for 10 tasks, poorly for 100 and not at all for 1000.

Tasks should be ordered, not tagged.

### Think about how to get it

If you can't get there from here, you probably don't want to go.  If you still want to go, you need to learn the way or find someone else who knows.

### Use someone else's solution

Spend your time wisely.  You don't have enough of it.  There's a lot more cool stuff to do in the world than you could possibly do.

### The size of your solution should match the size of your problem

Don't use a sledge hammer to swat a fly.  Don't use [CORBA](https://en.wikipedia.org/wiki/Common_Object_Request_Broker_Architecture) to pass a message.

### Recognize when solutions aren't

If a solution to your problem causes a bigger problem, it's not a solution no matter how cool it is.

### Describe what you want, not how to get it

It's more clear to think about what you want and it's easier to reason about states than transitions.

This works for both people problems and computer problems.

Procedures obscure the goals.

### If you have to write a procedure, it should be idempotent

Did I do it already?  Who cares, just do it again.

### Whenever possible, failed procedures should be resumable.

It broke half-way through.  Fix it and run it again. It shouldn't have to do the same work twice.

### Don't allow failure to be a habit

Things should succeed.  If you have to run things many times until they finally succeed, it's broken.

### Never count on initialization order

There are too many moving parts to know exactly when they will move.

### If explanations become work then they're too complicated

Complex documentation indicates poor abstractions.  Fix the program and the documentation becomes easy to write.

Detailed does not mean complex.  Intricate doesn't, either.

### Sufficiently detailed documentation is executable.

Can a computer do it?  If not, you didn't document it well enough.  You can't document judgment calls, so a computer can't do them.  You *can* fake it with a good heuristic but don't mistake it for judgement.

### Measure it

Your guess is probably wrong.  Measure it, don't guess.

### Keep an eye on it, but not yours

It's not enough that it worked, it has to keep working.  Computers are good at watching things.  Humans aren't.

### Don't ignore alerts

Any time you get an alert, your goal should be to make sure you never get it again, one way or another.

If you're not going to fix it it should be on a status page, not an alert.  Alerts are for taking actions.

### If everyone owns it, no one owns it

Make sure someone is accountable.  Make sure they have a backup (vacations, busses...)

Team wide alerts train everyone to ignore issues.

### Keep Thinking

There are very few problems that are not better solved by stopping to think about the best solution first.
