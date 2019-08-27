# Tuesday August 27th, 2019 Daily Coding Journal

23:22 — Here’s what my day at the office looked like today:
```
7:50 - 8:00
Connected mouse + keyboard

8:00 - 9:15
Scrum meeting
Completed Redux-Saga task 3
Discussed Redux-Saga flow with team leader

9:15-10:15
Redux-saga flow + syntax review

10:15 - 10:40
Continued Redux-saga flow discussion with team leader

10:40 - 11:45
Redux-saga flow + syntax + axios deeper understanding dive

11:45 - 12:45
Lunch

12:45 - 1:30
Read Lodash documentation to gain a surface level understanding of the library and its most common functions/methods.

1:30 - 2:05
Solidified Redux-Saga knowledge with team leader and prepared for final task — rewriting all Redux-Saga code from scratch to make a call to a mock API.

2:05 - 5:05 
Completed final Redux-Saga task to 90% completion.

After Office Hours

5:05 - 5:20
Debugging final Redux-Saga task with team leader.

5:20 - 5:40
Walking/Stretching body break.

5:40 - 6:00
Take notes on team leader's advice for debugging final Redux-Saga task

6:00 - 7:05
Deleted all of the code from today and attempted to complete the entire Redux-Saga task again from scratch. Close, but not entirely successful.

Notes I took while at the office today:

Redux/Redux-Saga NOTES

Try/catch/throw are JavaScript keywords that we can use in conjunction to deal with errors. Let’s talk about each of these keywords in more detail:

The try statement — Lets us test a block of code for errors.

The catch statement — Used to handle errors.

The throw statement — Lets us create custom errors.

The finally statement — Lets us execute our code even after our try and catch, regardless of the result.

Components and containers may sometimes be used interchangeably. Generally speaking, however, containers are “smart” and contain business logic plus need redux while components are “dumb” contain no business logic and don’t need redux.

Middlewares are snippets of code we integrate into our app to improve the flow of actions in the app and keep code clean and logical.

The goal of a reducer is to modify some specific part of an app’s state.

Sagas are used to execute some code after an action is dispatched.

A selector is basically a function that knows how to get a certain piece of data from the Redux store.

By using the createSelector( ) method, we can memoize our selectors. By doing this, our selector functions will only be executed when the part of state they are watching changes. In other words, memoized selectors are only executed when they are needed.

The purpose of reselect, a basic “selector” library for Redux, is that by this library’s memoizing of our selectors, our selectors become more efficient.

Selectors are used to avoid duplicating data in Redux, and to make our code more maintainable (future changes only need to be made in one place rather than in every related component)

Here’s another way of looking at Redux flow. 
UI —> Actions —> middleware(if we have the api call) -> Reducer —> Store —> State -> UI
The UI triggers actions which are sent to the reducer which updates the store that contains the state which defines the UI.

Redux alone supports only synchronous data flow. One motivation for using middleware like redux-saga, redux thunk, or redux-promise is the ability to make async calls (side effects). 

In redux-saga, Generator functions are used to implement Sagas.

The plain JavaScript objects we yield from generator functions are called Effects.

An Effect is basically an object that contains information we want to be interpreted by the middleware (in this case, redux-saga).

In other words, Effects are like instructions to our middleware to perform some operation such as dispatching an action to the store, or invoking some async function.

The Redux store is basically a big javascript object that stores all of the our application’s state.

We connect our store to our application using provider from react-redux.

mapDispatchToProps will map redux actions to the container’s properties

Redux actions are plain JavaScript objects.

In Redux-Saga, the call keyword is used for making asynchronous calls (for example, an axios request).

In Redux-Saga, the race Effect allows us to trigger a race between two Effects. Whichever Effect completes (resolves/rejects) first is used and the “loser” Effect is automatically canceled.

When we receive data from a web server, the data is always a string. Fortunately, using JSON.parse, we can convert that data into a JavaScript object (assuming the text was written in JSON format).

Async/Await NOTES

Async functions either return a promise, or in the cases a promise is not returned… JavaScript automatically wraps the returns value inside of a resolved promise.

The await operator is used to wait for a Promise. It can only be sed inside of Async code blocks.

The Promise.all( ) method returns a single Promise that is resolved when all of its promise pass, or when it contains no promises. The Promise.all( ) method if rejected as soon as any of its promises reject.

Axios NOTES

Axios is a popular JavaScript library used to perform HTTP requests.

Axios is both browser and Node.js compatible.

There are several reasons to use Axios instead of JavaScript’s native fetch API. Here are a few of them:
— Axios easily supports older browsers.
— Axios offers the ability to abort a request.
— Using Axios we can set a response timeout.
— Works in Node.js
— Performs automatic JSON data transformation

A response timeout is basically how long we’ll wait for our requested resource before throwing an error.

In Axios, the default timeout is set to 0. This means that by default our requests will never timeout which means users could be left waiting indefinitely!

Lodash NOTES

Lodash is a JavaScript library that helps us more write more concise code for many of the most common programming tasks.

By convention, the underscore character is set equal to the Lodash library.

The Lodash library has a few hundred method/functions. Some of the most important ones include:

_.find — Used to easily find an object within an array, or find an object that has multiple properties.

_.get — Used to return a property value from an object. If the path does not exist, undefined will be returned (or you can also specify a default value (third argument).

_.set — Used to set a property with a value. If the path does not yet exist, one will be created.

_.pick — We can use this method to pick properties from an object to return a new object.

_.omit — The opposite of the _.pick method. This method creates an object that has all of the properties of the initial object except those we choose to omit. The _.omit method is significantly slower than the _.pick method.

Some questions I thought about today while at the office:

Is the difference between _.get and bracket notation simply that _.get offers the ability to return undefined and optionally set a default value?

What is the difference between a property and a property path?

How do forks/spawns work in Redux/Saga?

How exactly does createStructuredSelector( ) work?
```
23:23 — Now I’m just doing a quick 10 minute review on arrow functions before bed.

23:24 — Apart from simply being shorter than regular function expressions, arrow functions are also different than regular function expressions because of the fact that error functions are not bound to the this, arguments, super, or new.target keywords. 

In other words… an arrow function doesn’t have its own this. An error function may take its this from its surroundings.

Arrow functions also do not have their own arguments object.

Arrow functions cannot be used as constructors and will throw an error if we attempt to use them with the new keyword.

Generally speaking, the yield keyword cannot be used in an arrow function’s body, This means that arrow functions cannot be used as generators.

23:35 -- Generally speaking, an arrow function cannot contain a line break between its arrow and its parameters. If this rule is not followed, we will get a syntax error.

Arrow functions are anonymous which can lead to them sometimes be harder to debug because we cannot track the exact line number where a bug occurred.

23:46 -- You know what I just realized after completing this journal entry? I'm pretty sure the reason my API call wasn't working when I tried to complete the task from scratch in after-office hours is due to the fact that I used an arrow function and attempted to access this.props using the arrow function.

I'm pretty sure tomorrow that if I use a regular function expression that my API call will work tomorrow! :D

23:48 -- In any case, it's really late now and I need to get some rest. Let's make tomorrow another day full of learning!
___
**Total time spent working as an employed developer today**: 8 hours 10 minutes

**Total time spent practicing coding outside of work today**: 2 hours 9 minutes

**Total time spent practicing coding outside of work thus far in August 2019**: 17 hours 9 minutes

**Total lifetime hours practicing code outside of a job**: 696 hours 48 minutes

**Total lifetime hours working as an employed developer**: 42 hours 50 minutes