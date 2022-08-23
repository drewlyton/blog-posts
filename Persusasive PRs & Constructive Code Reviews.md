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

## 3 Tips for Constructive Code Reviews
### 1. Review solution - not style.
This is pretty obvious, but it always bares repeating.  A code review is not the space to have conversations about code style or cleanliness. Those conversations should happen with more clear, generalized examples. In essence, those conversations should be, "Next time" notes that do not block the PR.

As a rule of thumb, the quality of the coded solution should be the focus of the review. That quality criteria is subjective, but 

### 2. Reply for resolution.


### 3. Approval by default.
