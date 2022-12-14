- Testing is hard, but incredibly important
- Gives you confidence to:
	- Scale your team
	- Ship faster / more often
	- Know that what you're building hits the feature requirements
- Then why do so many startups not write tests?
	- Usually a team of 2 engineers
	- It feels slower
	- Requirements change so often as the product is iterated on that writing tests feels like a recipe for a refactoring disaster
- These things are all true, but the decision to not write *any* tests creates a new problem if you end up getting out of the trough of sorrow
	- You don't have a testing culture
	- Now you're scaling your team and shipping faster without knowing whether or not the code works or if it's hitting the requirements. You have no confidence because you have no established culture around testing.
- So, then how do you transition to a testing culture?
	- Can feel so daunting - especialy with a large codebase.
- But we're engineers, we're not afraid of solving hard problems. Let's use the tools we have and automate the transition.
- Setting up the rules
	- Level 1
		- No direct code pushes - PR needed
		- PRs require review from another engineer
			- This has the added benefit of more than one person knowing about a section of the codebase
		- Build has to pass in CI before merge
	- Level 2
		- Setup test runners for unit, integration, and end-to-end testing
			- This isn't trivial, but senior engineers should dedicate time to it
			- Goal is to make it *easy* for the rest of the team to write tests
				- Have an internal hackathon or lunch-and-learn where everyone gets hands-on help using the new testing tools on *real code*. Outcome is everyone gets to pat each other on the back that "we're testing our code now"
		- Setup linting rules
		- Run the test suite and linter in CI
	- Level 3
		- Coverage threshold for new code
		- Coverage goal for team
			- What gets measured gets moved