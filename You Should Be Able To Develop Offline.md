- Forces you to think about decoupling and abstracting away 3rd party APIs
	- Only testing the code YOU wrote
	- If Auth0 is down, but your auth code works - it's a problem with Auth0
- Development speed
	- No need to wait for outbound requests (especially on unstable connections)
- Enables your team to be productive anywhere
	- Can work on an airplane or in the middle of the woods


This week, working remotely meant something a little different. My office was a lake-side cabin on the border of the U.S. and Canada. And this experience left me thinking about the importance of local-first development.

So, in this post, I want to share why I think we should always architect our development environments to work offline.

## Always Abstracted, Decidedly Decoupled.
Decoupling and abstraction are definitely software buzzwords people pass around in meetings to impress their bosses. However, even with their diluted conversational value, they are still extremely important practices.

Abstracting is the process of removing attributes and details of a system that aren't generalizable to its function. Decoupling is the process of breaking those systems into smaller pieces. Utilizing these design principles makes our code (*in theory*\*) more readable, portable, and iterable. And I believe that designing our applications for offline development creates a forcing function for well abstracted and decoupled code.

*\* I say "in theory" because abstracting and decoupling is a balancing act of separating systems while still keeping the code cohesive and easy to understand.*

### Let's talk about 3rd Party APIs.
I think leveraging external APIs is an amazing cheat code for product engineers. And, in a way, these vendors are providing abstractions to complicated processes like authentication, image optimization, and server hosting.

However, without abstracting these abstractions (oh boy), we can find ourselves starting the process of "vendor lock-in". Using the interfaces and packages these services provide across our application code can create a tight coupling between us and that provider.

And if that vendor doesn't have great solutions for [offline development](https://auth0.com/docs/get-started/applications/work-with-auth0-locally), we suddenly require an internet connection to work on our apps. Even worse, we can find ourselves in situations where if our vendor is experiencing an outage, we can't work on our application.

Designing for local development helps us find where we need to create abstractions that decouple our apps from vendors, internal APIs, and other external systems.

### Let's talk about mocking.
A powerful strategy for "fixing" apps that can't be developed offline because they are tightly coupled to external systems is request replaying or mocking. There are fantastic tools out there like [Mock Service Worker](https://mswjs.io/) that make it incredibly easy to listen for, intercept, and respond to external requests. However, with great power comes great responsibility, and I'm here to say that **we can get mocked by our mocks**.

Mocks that become out of sync with reality, just like tests that focus on implementation instead of outcome, can end up causing a maitenance nightmare. I experienced this first hand while working on Lumastic.

In the beginning, we didn't have a great strategy for integration and end-to-end testing across our GraphQL API and PWA. So, to test features of our client-side application, we ended up mocking essentially every response from the backend. As you can imagine, this was a nightmare to keep up with, and very quickly our mocks became out of sync with reality.

So, we changed our strategy. Instead of mocking the backend, we created a test environment for the API that we could run alongside our client-side test-runner. *Real* requests went out to a *real* API environment which gaves us *real* confidence in the code we were shipping to our users.

Mocking is incredibly powerful, but it shouldn't be a default strategy. Our systems should always have a **bias towards reality**.

## Internet Independence.
There are also some more obvious benefits to developing entirely locally. The first is that **local lacks latency**. This means that development speed is no longer proportional to internet speed. Although, if we're honest, the speed of Google and StackOverflow results is probably a larger latency factor than application network requests 😂. 

Lastly, I travel a lot. So, being able to work on an airplane, in the car, or in a cabin fully off-grid is a huge boon for my own productivity and lifestyle.

## Think Global, Develop Local.
Developing locally might seem unintuitive and feel almost backwards in our "one click global deployment" internet age. But I hope this article inspires you to think more about the benefits and tradeoffs of the approach.

If you have questions, comments, or concerns regarding local development, please reach out to me on Twitter. Also, if you have strategies for achieving local development with complicated tech stacks, I'd love to hear them!

Until next time.