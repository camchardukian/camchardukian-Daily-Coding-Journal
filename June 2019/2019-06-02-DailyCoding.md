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
 ___

___
**Total time spent coding today**: 

**Total time spent coding  thus far in June 2019**: 

**Total lifetime hours of coding**: 

