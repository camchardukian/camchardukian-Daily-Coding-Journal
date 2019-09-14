# Saturday September 14th, 2019 Daily Coding Journal

19:30 — Yesterday I went home from work early with a fever, and I’m still not feeling great to be honest. With that being said, I’m going to try to put in 1 hour getting better with Redux.

I’m going to go through [Dan Abrahamov’s course](https://learnreduxwithdanabramov.com/) on Redux basics.

Hopefully I’ll be much more comfortable with Redux by the end of it.

19:37 — Here are my notes for video one in the course — [Redux: The Single Immutable State Tree](https://egghead.io/lessons/react-redux-the-single-immutable-state-tree):

— Everything that changes in our application, including the data and the UI state is contained within a single object we can refer to as state or the state tree.

19:40 — Here are my notes for video two in the course —
[Redux: Pure and Impure Functions](https://egghead.io/lessons/react-redux-describing-state-changes-with-actions): 

— The state tree is read only. You cannot modify or write to it. The only way of changing the state tree is by dispatching an action.

— An action is a plain JavaScript object that describes how we want to change the state in our application.

— The only requirement of an action is that is has a type property which is not undefined.

— It’s recommended that we set the types of our actions to a string. The reason strings are recommended is because they are serializable. My attempt at paraphrasing [Wikipedia’s page on serialization](https://en.wikipedia.org/wiki/Serialization) is that serialization is basically the process of taking data structures or object state, and putting into a format that can be stored/transmitted, and reconstructed later.

— Any data that gets into a Redux application (whether is it initiated by user interaction or a network request), gets into our application via actions.

— One benefit of using actions in our application rather than changing state directly is that other developers do not need to know exactly how another developer implemented some form of state change. The only thing the new and/or less skilled developer needs to know is which which action they need to dispatch to initiate the desired state change.

22:19 — Just took a couple hours break for dinner, to hang out with my girl a little and because my back is seriously sore from being sick and having to sit or lie basically all of the last 30 hours. In any case, video 3 notes -- [Redux: Pure and Impure Functions](https://egghead.io/lessons/react-redux-pure-and-impure-functions):

— Side effects are things such as network or database calls. Impure functions have side effects while pure functions don’t. In other words, pure functions are predictable because if you call a pure function with the same set of arguments you’re going to get the same value returned. This isn't always the case with impure functions.

— Dan says that this distinction is important because some of the functions we’re going to write in Redux are required to be pure, and thus we should know what a pure function is.

22:25 — Video 4 notes — [Redux: The Reducer Function](https://egghead.io/lessons/react-redux-the-reducer-function):

— Anytime we change the state of our application, we can’t actually change the state directly. What we actually do is create a new object for the whole state of our application. You may expect this to be slow. The reason Redux doesn’t suffer from poor performance, however, is that Redux can still refer to the previous version of state for everything that has not changed.

— To mutate state, we need to write a function that takes the previous state of the app, and a dispatched action before returning the application’s new state. This function has to be pure. This function is called a reducer.

22:37 — Video 5 notes — [Redux: Writing a Counter Reducer with Tests](https://egghead.io/lessons/react-redux-writing-a-counter-reducer-with-tests):

— If we dispatch an action that the reducer does not understand, the reducer should return the current state of the application. This is why we often see code at the end of the reducer that says
```
default: return state;
``` 

22:56 — Video 6 notes — [Redux: Store Methods: getState(), dispatch(), and subscribe()](https://egghead.io/lessons/react-redux-store-methods-getstate-dispatch-and-subscribe):

— The Redux store holds our application’s state object, it lets us dispatch actions, and when we create the store we need to specify the reducer that will tell us how our state is updated via the actions dispatched to our reducer.

23:04 — Video 7 notes — [Redux: Implementing Store from Scratch](https://egghead.io/lessons/react-redux-implementing-store-from-scratch):

— We calculate the new state of our application by calling a reducer with the current state and the action that was dispatched to the reducer.

23:24 — Despite being sick, by goal for today was to spend an hour getting better at one of my weaknesses — Redux. I achieved that so I’m happy to have taken a small step forward to better understanding Redux and overcoming this weakness.

Tomorrow, I’ll try to finish taking notes on the rest of Dan’s course so that if I'm well enough to go to work on Monday, I'll hopefully no longer find redux *exceedingly* difficult.

That will be challenging as there are still 23 videos left. However, at 15 minutes or so per video, that mean I’d need just under 6 hours to finish the course.

So… we’ll see how that goes ;)

___
**Total time spent working as an employed developer today**: N/A

**Total time spent practicing code outside of work today**: 1 hour 29 minutes

**Total time spent practicing code outside of work thus far in September 2019**: 18 hours 46 minutes

**Total lifetime hours practicing code outside of a job**: 719 hours 21 minutes

**Total lifetime hours working as an employed developer**: 137 hours 36 minutes