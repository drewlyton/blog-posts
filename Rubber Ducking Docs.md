One of my favorite books on software engineering is (of course) *The Pragmatic Programmer*\* by [Andrew Hunt](https://en.wikipedia.org/wiki/Andy_Hunt_(author) "Andy Hunt (author)") and [David Thomas](https://en.wikipedia.org/wiki/Dave_Thomas_(programmer) "Dave Thomas (programmer)"). First published in 1999, this book is a timeless classic that I can't recommend enough.

Among the many nuggets of wisdom in this wonderful read is ["rubber ducking"](https://en.wikipedia.org/wiki/Rubber_duck_debugging). This is a method of debugging that involves simply explaining the problem either verbally or in writing. Usually, by externally communicating the issue, an untested assumption is presented that leads to finding the solution.

## Ducks with documentation.
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

Obviously, writing this doc provides the same value as traditional, verbal rubber ducking. However, the real power of documenting the debugging process comes into play when...

## Asking for help.
Let me know if this conversation looks familiar:

---

*Player_1: Hey - you got a sec?*
<div style="text-align: right">Player_2: Yeah, what's up?</div>
*Player_1: I'm having an issue getting the app to build.*
<div style="text-align: right">Player_2: What's going on?</div>
*Player_1: I'm running the right command in the terminal, but it's throwing an `AMBIGUOUS_ERROR_MESSAGE`*
<div style="text-align: right; max-width: 60%; float: right;">Player_2: Mmm weird. I've got a meeting in 10 minutes, but let's screen share when I get off - shouldn't be more than 30 minutes.</div>
*Player_1: Sounds good 👍*

---

What just happened? Well, Player_1 and Player_2 had a conversation about an error Player_1 is experiencing. They left that conversation with Player_2 still having no understanding of the problem and Player_1 still having no actionable solution to test other than, "wait 30 minutes".

This conversation was a *waste of time*. Both parties entered and exited in the same state. This is an example of what I see as *conversation* - not *communication*. Let's see how this scene changes if Player_1 already made a *Rubber Ducking Doc*:

---

<div style="max-width: 70%; float: left; font-style: italic;">Player_1: Hey Player_2, I'm experiencing an error when I build the app. Here's a doc that explains the issue and what I've tried so far. I'd love to get your thoughts and ideas for possible solutions whenever you get the chance.</div>
<div style="text-align: right; max-width: 70%; float: right;">Player_2: Cool 👍 - I'll take a quick look right now.</div>
*Player_1: 🙏*
<div style="text-align: right; max-width: 70%; float: right;">Player_2: I've got a meeting in 10, but try______. I had a similar issue a few months ago and that worked for me.</div>
*Player_1: That worked!! Thanks!*

---

What changed? Well, to get help with their issue, Player_1 was able to just *send the doc* to Player_2. That doc contained all the relevant information and context which made it easy for Player_2 to come up to speed and provide deep, meaningful, actionable feedback instantly.

In this example, the solution recommended by Player_2 worked. However, even in the case where it didn't, *there was still no wasted time*. Player_1 would have still been able to test the solution and gain new information even while Player_2 was on their meeting. No one stayed blocked because of someone else's calendar.

But wait, there's yet *another* use for this document once a solution has been found...

## It's a draft.
Writing internal memos or technical blog posts is a *fantastic* way of sharing your lessons learned and giving back to the community. But after solving a major issue, the last thing I want to do is stop working and write an essay. 

Luckily, because of the *Rubber Ducking Doc*, I don't have to. All of the information needed for a future writeup is in that document: *Problem*, *Solution*, *Lessons Learned*. In fact, depending on how clearly you wrote initially, you could just send it as is to your teammates as an internal memo.

*Rubber Ducking Docs* are great for organizations and individuals who struggle to come up with technical content ideas. Personally, writing these docs while working on projects has given me a *huge* backlog of blog post ideas that I don't think I'll ever be able to deplete.

Every problem you've experienced is currently being or will be experienced by someone else. Share the things you've learned the hard way so - hopefully - they don't have to.

## Try it out!
I hope you'll consider trying out *Rubber Ducking Docs*. If you use a similar system or try this one, please let me know [on Twitter](https://twitter.com/drewlyton). I'd love to hear your experiences with "rubber ducking".

Until next time.

\*Thanks goes to Keith Stolte for giving me *The Pragmatic Programmer* for Christmas last year. 