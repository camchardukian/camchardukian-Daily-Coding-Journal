# Sunday June 2nd, 2019 Daily Coding Journal

11:42 -- Here we are, let's learn some more about Redux. Let's continue taking notes from [part IV](https://www.youtube.com/watch?v=Lt4P9BKOPfI) of Techsith's series on learning Redux.

11:45 -- Here are some notes from the second half of the video...
* Remember that each child in an array or iterator should have a unique "key" prop (Bob also explained this in his [*Learn React for Free*](https://scrimba.com/playlist/p7P5Hd) course on Scrimba.)
* By convention you should use uppercase letters for your actions defined within dispatch.

11:54 -- I've finished the fourth video in his series.

11:57 -- I'm going to start going through the Redux exercises on FreeCodeCamp.

11:58 -- Here are some important notes from the [first lesson](https://learn.freecodecamp.org/front-end-libraries/redux/create-a-redux-store):

* Redux is a state management framework that is often used with React, but that is also compatible with many other web technologies.
* In Redux, the entire state of our application is controlled by a single state object housed in the Redux *store*.
* In Redux, the Redux store is the single source of truth when it comes to application state.
* Anytime you want to update state, you must do so through the Redux store.
* Given the previous fact, your flow of data will be unidirectional (flowing in only one direction). This makes is easier to track state management in your application.
* The method createStore() is called on the Redux object to create the Redux *store*.

12:04 -- I just finished writing my first line of Redux!

I declared a store variable and assigned it the evaluation of the createStore() method with a reducer passed in as the argument.

Here's the code I wrote to accomplish this task:
```
const store = Redux.createStore(reducer)
```
Things were made a little bit easier given that FCC hade already predefined the reducer.

 Fortunately, I'll practice writing a reducer function in later challenges!

 12:10 -- Notes from [exercise #2](https://learn.freecodecamp.org/front-end-libraries/redux/get-state-from-the-redux-store):
 * It's possible to retrieve the current state held in the Redux store object using the getState() method.

 12:14 -- I just completed the 2nd coding challenge. Here's the code I wrote:
 ```
const currentState = store.getState()
 ```
 The above code takes the value of our store's state using the getState() method. We then take whatever state was retrieved and assign it to the currentState variable.

 12:15 -- I'm going to do one more exercise before cooking lunch.

 12:16 -- Here are my notes from [exercise #3](https://learn.freecodecamp.org/front-end-libraries/redux/define-a-redux-action):
 * One of Redux's core tasks is updating states.
 * In Redux, all state updates are triggered by dispatching actions.
 * Actions are JavaScript objects. These JS objects contain information about an action event that has occured.
 * When the Redux store receives action objects, it will update its state accordingly.
 * Actions must carry a *type* property that specifies the "type" of action that occured.

 12:20 -- Here is a snippet of code I created to declare my first action in Redux:
 ```
const action = {type: 'LOGIN'}
 ```

 12:21 -- I believe that in the above example the naming of the variable is somewhat arbitrary. 

 In other words, I named by action object "action" because that's what the FreeCodeCamp tests were looking for.

 Given that we are likely to have multiple actions in our applications, however, I'm sure that we must have flexibility in naming our actions the same way we have flexibility in naming JS functions.

 12:23 -- I'm going to take a break for lunch. Today I'm teaching myself how to cook broccoli haha. See you later!

 12:40 -- Having to reconfigure a bunch of stuff on GIT due to having directly made a change on GitHub instead of using the terminal.
 ___
15:08 -- I'm back. Cooking the broccoli was interesting haha. I want to learn to cook to save money so that I can spend less time working for "fast cash", and instead spend more time investing in myself learning web development.

15:10 -- Here are my notes for [Redux exercise #4](https://learn.freecodecamp.org/front-end-libraries/redux/define-an-action-creator):

* After you create an action, the next step is to send that action into the Redux store so that the store can update its state.
* Action creators are JavaScript functions that return an action.

Here's an example of an action creator I wrote to pass this exercise's challenge:
```
function actionCreator () {
    return action
}
```

15:18 -- On to [Redux exercise #5](https://learn.freecodecamp.org/front-end-libraries/redux/dispatch-an-action-event):

* The dispatch method is what you use to dispatch action to the Redux store.

* It's important to note that when we're working with the dispatch method, we can pass it either an action object directly, or indirectly (via an action creator that will return an action)

Here's an example (that I just finished writing) of calling the dispatch method on our store and passing in the action creator loginAction() (which would eventually return type: 'LOGIN')

```
const store = Redux.createStore(
  (state = {login: false}) => state
);

const loginAction = () => {
  return {
    type: 'LOGIN'
  }
};

store.dispatch(loginAction());
```

15:24 -- I'm going to take a quick break. Then, we'll continue with exercise #6...
___

15:37 -- I'm back. Let's continue with Redux exercise #6 (out of 17):

* After an action is created and dispatched, the Redux store needs to know how to respond to that action. This is the job of a reducer function.
* Basically, actions lead to a demand to modify state and the Reducer is responsible for executing on that demand.
* A reducer takes two arguments -- state, and action.
* A reducer always returns a new state.
* A key principle in Redux is that state is read-only
* Our reducer function must never modify state directly. It should instead return a new copy of state.
* Redux does not enforce state immutability, though it is wise for you to force immutability using your reducer functions.

Solving this exercise's challenge was a bit of a headache, but here's my solution:
```
const defaultState = {
  login: false
};

const reducer = (state = defaultState, action) => {
  // change code below this line
if (action.type === 'LOGIN') {
  return {login: true}
}
else {
  return state
}

};

const store = Redux.createStore(reducer);

const loginAction = () => {
  return {
    type: 'LOGIN'
  }
};
```

15:54 -- I'm on [exercise #7](https://learn.freecodecamp.org/front-end-libraries/redux/use-a-switch-statement-to-handle-multiple-actions/) now. Here are my notes:

* It's possible to tell the Redux store how to handle multiple action types.

* It is very common to use a JavaScript switch statement when writing out reducers.

* When our app has multiple reducers, they are all run any time an action dispatch is made... even when the action isn't related to that reducer.

Feeling a bit stuck on this challenge...

16:08 -- I'm feeling gassed right now. I'm going to have to come back when I have more energy.
___
**Total time spent coding today**: 1 hour 54 minutes

**Total time spent coding  thus far in June 2019**: 3 hours 29 minutes

**Total lifetime hours of coding**:  574 hours 48 minutes

