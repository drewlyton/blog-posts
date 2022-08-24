One of my favorite books on software engineering is (of course) *The Pragmatic Programmer*\* by [Andrew Hunt](https://en.wikipedia.org/wiki/Andy_Hunt_(author) "Andy Hunt (author)") and [David Thomas](https://en.wikipedia.org/wiki/Dave_Thomas_(programmer) "Dave Thomas (programmer)"). First published in 1999, this book is a timeless classic that I can't recommend enough.

Among the many nuggets of wisdom in this wonderful read is ["rubber ducking"](https://en.wikipedia.org/wiki/Rubber_duck_debugging). This is a method of debugging that involves simply explaining the problem either verbally or in writing. Usually, by externally communicating the issue, an untested assumption is presented that leads to finding the solution.

## Debugging by documenting.
Employing this tactic has helped me avoid banging my head against my computer for days on end countless times. The constant practice of explaining bugs and issues has also made me faster at triaging them. I'm calmer and more confident when fires pop up, and it's easier to see patterns that link the current problem to another I've seen before. 

Rubber ducking has become such an important part of my practice as an engineer that I actually created what I call a *Rubber Ducking Doc*. This is a single page template with questions that prompt me through the process of communicating the issue at hand.

The template is inspired by issue documentation requirements for open source projects - with a little added flavor ✨. I pull one of these up whenever I've spent longer than 25 minutes working on a problem. It looks like this:

---

### *What's the problem?*
*Write a brief description of the issue. Dump error logs, screenshots, and other undesirable outputs from the system.*

### *How do I reproduce the problem?*
*What are the steps that produce the exact error above? Can I easily turn those steps into an automated test to make debugging faster going forward?* 

### *Have I seen a similar problem before?*
*Write down related issues that were solved and how they were solved.*

### *Have others seen this problem before?*
*Google the problem. What have other people experienced? Be sure to copy the links to any relevant threads/discussions for safe keeping.*

### *Solutions to test*
*Dump the ideas for solutions that have come up while writing this doc. What assumptions need validation? What new information do I need to move forward?*

### *Notes*
*Keep track of relevant findings, observations, and research as solutions get tested.*

---



## The real value is in *sharing*.


\*Thanks goes to Keith Stolte for giving me this book for Christmas. 