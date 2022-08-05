As a product designer and engineer, I'm constantly learning new tools and techniques to make my applications performant, usable, and maintainability. These three pillars of product are table stakes of the industry. However, I feel there is a fourth pillar that sets apart the products and product teams that make it a focus: ***insight***.

## What are insightful applications?
*Insightful* applications measure and synthesize metrics of performance, usability, and maintainability in order to minimize assumptions and bias. Insightful applications provide visibility, transparency, and clarity into what is and isn't working. They save teams the time spent in grid-lock arguing about what "feels" right, and enables teams to say, "Why argue what we can test?". This data-driven approach to development bolsters collaboration, experimentation and creativity.

At its core, designing for insight is about knowing what measurements matter most for the product. Then, it's about creating systems for monitoring analytics that make those metrics meaningful to the team. The latter is usually much harder because it requires alignment and adoption across departments (engineering, design, and management).

## Types of analytics
In most cases, there are three types of analytics: descriptive, diagnostic, predictive, and prescriptive. Each product requires its own balance of all four to provide adequate insight to its maintainers.

**Descriptive** analytics tell us *what happened*. A user visited a page, clicked on a button, and then the app crashed. This is incredibly valuable information. Especially when aggregated, descriptive analytics can show the most common features, workflows, and points of failure in our applications.

**Diagnostic** analytics take it a step further and tell us *why it happened*. For example, the app crashed *because* there was a runtime type-mismatch error in the onclick handler for that button. This provides much more true understanding of issues and user behavior.

**Predictive** analytics tell us *what could happen*. For instance, let's say an average of 100 users try to click on that button every day and the button is the signup button. That means we'll lose 700 new users over the course of the next week.

**Prescriptive** analytics tell us *what should happen*. Compared to all of the errors in the system, this one is the most impactful to the businesses bottom line and should be solved as soon as possible.

## Tools of the trade
There are a fair amount of plug and play tools that can be added to our applications to build systems of insight. Here are some of my favorites:

### [LogRocket](https://logrocket.com/)
A complete hub for product analytics - combining event capture, performance/error monitoring, and complete session replay. With LogRocket, you can quickly debug errors by getting a visual replay of your users interacting with your application. It's amazing.

### [Mixpanel](https://mixpanel.com/)
Great for tracking user events and interactions. Wonderful data visualization tools and integrations with other analytics providers (i.e. LogRocket).

### [Amplitude](https://amplitude.com/)
A cheaper, slightly worse Mixpanel (imo). Great for consumer applications with a ton of traffic.

### [Sentry](https://sentry.io/welcome/)
A best-in-class monitoring platform for APIs and full stack web applications.

### [HotJar](https://www.hotjar.com/)
 Similar to LogRocket's session replay feature, HotJar shows and aggregated heat map of your website to see where users focus their attention and interact. Best for marketing and sales websites to help provide insight around conversion metrics.

## Making measurement meaningful
Capturing analytics is only half of the story when it comes to building systems for insight. The other half is adjusting and iterating the team's workflow to use these data to make informed product decisions.

Having a dashboard that's always on a TV in the office or up on everyone's screen during product meetings is a great place to start. These practices create a data-driven culture where individual ego and opinion is quelled in favor of the actions and behaviors of actual users.

As a side note, please remember that collecting data of any kind should spark rigorous discussions with teams and stakeholders regarding privacy, security, and integrity of that data. Code responsibly.

Now, go forth and **build, measure, learn**.