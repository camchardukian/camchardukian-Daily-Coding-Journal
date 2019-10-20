# Sunday October 20th, 2019 Daily Coding Journal

18:55 — Alright, today I’m going to study an hour or so about lifecycle methods in React. While I’ve gotten a lot more solid with basic React principles and Redux-Saga over the last few months, my team leader has said I would greatly benefit from strengthening my knowledge of lifecycle methods in React.

18:56 — To be honest, I’ve been feeling kind of out of it today. Last night I did not sleep well at all, and today I had an early morning of work at my side hustle of teaching English.

In any case, it was a lot of effort getting myself to this coffee shop to get some work done. Let’s get started and take another small step toward becoming a better developer.

18:58 — To get started, I’m taking some notes from [this article on React lifecycle methods](https://programmingwithmosh.com/javascript/react-lifecycle-methods/) from Mosh Hamedani:

— While I didn’t know it until now, *render()* is actually a lifecycle method in React. This is actually the most common lifecycle method, and the only lifecycle method you are required to use in class components in React.

— If there is nothing inside of a component to render to the screen, the *render()* method will return *null*.

— You cannot update the state of your component within the *render()* method because React requires *render()* to be pure. In other words, the output of *render()* should always be the same for any given set of inputs.

—While it is possible to modify our component’s state within the *componentDidMount()* lifecycle method, Mosh recommends doing so with caution. The reasoning behind this is that modifying component state inside of componentDidMount can sometimes lead to performance issues.

— The *componentDidUpdate()* lifecycle method is most commonly used for updating the DOM to respond to prop or state changes.

— It’s important to note, that while we can use *setState()* inside of *componentDidUpdate()*, we should be conscious of including a condition that compares the current state of our application to previous states. If we fail to do this, it’s possible for our application to get stuck in an infinite loop.

— The *componentWillUnmount()* lifecycle method is called just before our component is unmounted and destroyed.

— It is *not* possible to use *setState()* within this lifecycle method. At first I didn’t understand why, but it turns out that the reason we cannot call *setState()* from *componentWillUnmount()* is that our component will not be re-rendered after calling *componentWillUnmount()*.

— Developers typically use *componentWillUnmount()* to perform different “clean up” activities. Some common examples include canceling API calls, learning timers, or clearing any caches in storage.

— While less popular than the lifecycle methods we’ve already discussed, another lifecycle method us React developers should be comfortable with is the *shouldComponentUpdate()* lifecycle method. 

— While I previously thought that components only re-rendered if their state “changed”, it turns out our components actually re-render anytime *setState()* is called at all. In other words, I *think* that if we set our state to a value that is identical to the current state, our component would still be re-rendered because it’s “technically” a new state.

— The benefit of using *shouldComponentUpdate()* is that their are certain cases where using it can lead to improved performance in our application.

— *static getDerivedStateFromProps()* is one of the newer React lifecycle methods that was introduced in the last 1-2 years.

— *static getDerivedStateFromProps()* runs just before the *render()* method. This method does not have access to “this” because it is a static function.

—*static getDerivedStateFromProps()* is used in the rare case where we want to update *state* in response to *prop* changes. If our state should change after running this method, *static getDerivedStateFromProps()* will return an updated state object, if there are no changes to state however, it will simply return null.

— One important thing to note is that *static getDerivedStateFromProps* runs immediately before **every** render of our component.

— *getSnapshotBeforeUpdate()* is another relatively new lifecycle method in React, whose purpose is more or less to replace the now deprecated *componentWillUpdate()*.

— *getSnapshowBeforeUpdate()* is run just before the DOM is updated and the value that it returns is passed to *componentDidUpdate()*.

19:52 — Well, it’s been a solid hour of studying. Now that I’ve spent some time studying how all of the different lifecycle methods work, I’m confident I’ll feel a lot less intimidated the next time I have to work with them.

___
**Total time spent working as an employed developer today**: N/A

**Total time spent practicing code outside of work today**: 1 hour 5 minutes

**Total time spent practicing code outside of work thus far in October 2019**: 17 hours 39 minutes

**Total lifetime hours practicing code outside of a job**: 751 hours 18 minutes

**Total lifetime hours working as an employed developer**: 334 hours 22 minutes