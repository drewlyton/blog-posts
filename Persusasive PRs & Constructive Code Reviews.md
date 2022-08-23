Working with branches, pull-requests, and code reviews is a must-have best practice when working on a production application at any scale (including a team of 1). When done well, the process catches bugs quicker, circulates knowledge of the codebase, and makes version control more valuable.

However, pull-requests and code reviews are also extremely susceptible to becoming useless, forgone formalities for teams. Without an intentional framework behind them, these tools can fester frustration rather than foster great communication.

So, in this post, I'm going to provide some tips for writing persuasive pull-requests and constructive code reviews that I've learned from working with great engineers. 

## 3 Tips for Persuasive PRs
### 1. Communicate the context.
A great PR description gives context to the code. Start by *explaining the problem* the code is solving. Attach issues and customer support tickets. Post screenshots and error messages.

Then, *explain the solution in words*. Run through how the code works while calling out added abstractions, packages, and refactors so that the reader understands at a high level what has changed and *why*.

A well-written description makes reviewing the PR *much easier* and more likely it will be approved without a long back and forth in the comments. It's a courtesy to the reader that goes a long way.

### 2. The author's review.
At Simple Thread, a coworker of mine introduced me to the concept of the *author's review*. This is essentially a practice of proof reading your PR before you request others for review.

It is extremely valuable for catching small errors, spelling mistakes, and lingering `console.log` statements. These small errors are wastes of time for an external reviewer to call out. So, find and fix them first.

The author's review also shows to an external reviewer that you've double checked your work. Adding comments and starting discussions preemptively about pieces of the code allows you to explain your decision making before its even questioned. It speeds up discussion and can eliminate a lot of back and forth during the review process.

### 3. Split by solution.
This one, I will admit, I rarely do. But, something I *strive* for is single-solution pull requests. This means splitting out commits that address orthogonal problems into separate branches. This makes each PR smaller and more succinct.

- Also reduces merge conflicts
- Reduces the blocks for other solutions if one can't be merged
- Reduces the work if we need to cherry pick
- Nicer to the reviewer because there's less context switching and everything is working together across the touched files

## 3 Tips for Constructive Code Reviews
### 1. Review solution - not style.
This is pretty obvious, but it always bares repeating.  A code review is not the space to have conversations about code style or cleanliness. Those conversations should happen with more clear, generalized examples. In essence, those conversations should be, "Next time" notes that do not block the PR.

As a rule of thumb, the quality of the coded solution should be the focus of the review.

### 2. Comment for immediate resolution.
Specify what's required of the author with each comment. When the author reads your review, they should essentially have a checklist of changes to make before merging. Their default reply to your comment should be "Resolve Conversation". 

Commenting for clarification is fine, but make sure to highlight that there is no action necessary and that changes are not required. However, if a back and forth conversation is happening in a PR, both parties should question the value and forum of the conversation. Maybe it's time to take it offline and pair a little.

### 3. Bias towards approval.
Having your PR blocked because of a few simple changes is annoying. Getting pinged to re-review a PR with minor changes is also annoying. A bias towards approval solves these problems for both parties.

Now, I'm not saying to "just auto-approve your PRs". That's a recipe for disaster - especially on teams with developers who are new to the codebase (or coding 😁). However, in situations where you're reviewing code of trusted team members and the path to approval is explicit and clear - approve the PR after commenting suggestions. 

Trusting your teammates to implement the changes and merge the PR in themselves. Merging becomes a shared responsibility and no one has to be DM'd in Slack with messages saying, "I made those edits - can you please approve my PR?"



This principle can be hard for some senior engineers and managers to adopt, but it goes a long way to bolstering the trust and speed of your team.

## Incorporate and iterate.
These tips are just that - tips. Like with all things, code review systems should adapt and evolve to fit the needs of the people in them. There are no rules or one-size-fits-all solutions. But I hope this article was helpful or give you some inspiration.

If you have tips to share or thoughts on mine, I'd love to hear about them [on Twitter](https://twitter.com/drewlyton).

Until next time.


**Notes**
- Adding qualitfication for approve by default
- Bonus tips for automating and controlling some of this with Git services