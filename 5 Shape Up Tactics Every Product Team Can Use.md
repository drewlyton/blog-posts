I try to steer clear of dogma. That's why I don't subscribe to any one method of developing products. Scrum, Lean, FDD, Kanban, Scrumban, XP, Spiral, etc. - they all have their strengths and weaknesses (yes, even *Waterfall*). There is no *right way* of organizing and developing product. 

I believe in learning many methodologies, trying out different ideas, and creating systems that work for the products I'm building and the teams I'm building them with.

*Shape Up* is a product development methodology that I think is well suited for this type of customization. Although it was developed at Basecamp - a company known for its dogmatic ways of working - most of the strategies they share in the book are malleable and portable.

At its core, *Shape Up* is really just a set of tactics designed to help teams focus on the most important aspect of product development: **the relationship between problem and solution**. So, in this post, I'm going to share five tools I find incredibly useful from Shape Up that any team can use.

## [1. Breadboarding](https://basecamp.com/shapeup/1.3-chapter-04#breadboarding)
Ideas are fickle. As they sit in our heads, we change, morph, and adapt them with each new conversation, requirement, and piece of feedback we receive. And this can sometimes lead us to lose the core concept of our solution. Soon we start asking things like, *"Wait, how does this all fit together again?"*

Breadboarding is a great way of externalizing our ideas and protecting them from the swirling tornado of new information that exists in the concept phase.

I think of breadboarding as a tool that sits at the intersection of storyboarding, wireframing, and concept mapping. Where each of the latter focuses on providing different levels of fidelity on look, feel, and flow - breadboarding focuses attention on how a product works and *nothing else*.

Let's take a look at a simple example:

![[Pasted image 20220826113612.png]]

Here you can see the three main pieces of breadboard diagrams:
1. **Places** - elements that display information to users.
2. **Affordances** - elements users interact with.
3. **Lines** - connections between affordances and places. 

Thinking about each element in a concept as one of these three patterns seems so simple that you might think it only works for trivial examples like the one above, but this process scales really well. You can outline the elements of an entire product with just a breadboard diagram.

The balance between action-based and visual-based design makes it great for guiding collaboration and garnering buy-in across engineering and UI teams. It's easy to find flaws, iterate quickly, and keep fleshing things out over time. And the incorporation of only high-level details makes sure you don't lose the forest through the trees.

And when it's time to get a little more visual, having a breadboard diagram makes it really easy to turn those *Places* into...

## [2. Fat Marker Sketches](https://basecamp.com/shapeup/1.3-chapter-04#fat-marker-sketches)
When prototyping new features or products, it's really important to match the level of visual fidelity to the level of understanding about the actual UX. If you don't know *where* the "Submit" button goes yet, you shouldn't distract yourself, your team, or your potential user with its color or even its copy. Our mockups and prototypes should operate like good scientific experiments - testing one variable at a time.

Fat marker sketches are a great tool for doing this. They're incredibly fast to create, iterate, and throw out if need be. They're also a great way for managers, engineers, and other non-designers to provide visual concepts to the design team without locking in a certain "look" or strict flow.

![[Pasted image 20220826132116.png]]

Notice how the sketch above for a simple todo-list grouping system conveys the key visual elements and *omits everything else*. There's no copy, color, or concept of space (like a page) or time (like a flow). This means the team can have a clear discussion internally or garner feedback from users about the key piece of visual language in question - the dividers - without distraction.

Once that piece has been solved, the design team can iterate again and test out another assumption. This process can continue piece by piece until the sketch starts looking more like a full visual protoype.

![[Pasted image 20220826133248.png]]

The sketched look still communicates that this is a "Work In Progress", but the important stuff - the UX - is all there.

Note that it's not enough to just design in grayscale with a tool like Figma. I love Figma, but it makes it too easy to be too precise too soon. That's why for both Breadboarding and Fat Marker Sketches, I recommend using a tool like [Excalidraw](https://excalidraw.com/).

## 3. The Pitch
I believe one of the biggest liabilities to a product team is a *bias towards building*. Some people disagree with that and often praise teams that "fail fast". But jumping from ideation to execution without rigirously mitigating risk and testing out assumptions is the worst fail condition. This bias usually presents itself on teams with heavy engineering backgrounds.

Solve the problem before you write the code. Centers scope around the problem at hand - not everything the solution *could do*. Having a standard doc for pitching features means that anyone can write these - including someone in engineering, customer support, or marketing. Product team becomes arbiters of vetting the ideas - not having to come up with all of them.

Can go look at the template yourself, things I want to call out:
1. Fixed time. Variable scope.
2. Rabbit Holes (problems created by the solution that should be thought through before implementation)

## 4. The Handoff 
Self organizing teams. Everyone needed on the project gets in the same room and works vertically. Collaborate on the same pitch. Teams create the tasks, track them however they want, create scopes, and write reports of how each scope is coming along.

## 5. Cycles & Cooldowns
Words matter. Stop sprinting. Two weeks is not enough time to do something really meaningful. Give teams the time and space to get things done with a true deadline. Allows for time afterwards to fix bugs, write more tests, reflect on the process, whatever. 



**Quick note:** This post discusses the concepts I like using from the product development methodology described in *Shape Up*. It does not mean that I condone [the idiotic beliefs and behaviors](https://www.theverge.com/2021/5/3/22418208/basecamp-all-hands-meeting-employee-resignations-buyouts-implosion) of the Basecamp founders or the author, Ryan Singer. I wrote about my thoughts on that situation [here](https://join.lumastic.com/stories/social-impact).