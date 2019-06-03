# Monday June 3rd, 2019 Daily Coding Journal

8:41 -- I was talking to a Vietnamese guy on Facebook who started coding in August 2018 and had a job 4-5 months later. *Why?*

Because he was dedicated to his craft putting in 8-10 hours a day of work. 2 hours a day isn't enough -- ESPECIALLY when I currently have few other obligations this summer.

I'm bleeding cash right now. I need to be more dedicated. Let's get to it!

8:58 -- I was stuck on the [*Use a Switch Statement to Handle Multiple Actions*](https://www.youtube.com/watch?v=S69RtiR6eR4) on FreeCodeCamp for close to 20 minutes.

I thought I had everything right and I even watched Youtube tutorials that seemed to confirm that fact.

Yet. I. Still. Couldn't. Pass. The. Challenge.

It turns out the only issue with my code was that I separate my return statement onto two lines when the user tests were expecting everything to be on one line. DOH O_O.

Anyway, here's the code I used to pass the test:

```
const defaultState = {
  authenticated: false
};

const authReducer = (state = defaultState, action) => {
  // change code below this line
switch (action.type) {
  case 'LOGIN':
  return {authenticated: true}
    case 'LOGOUT':
    return {authenticated: false}
  default:
return state
}

};

const store = Redux.createStore(authReducer);

const loginUser = () => {
  return {
    type: 'LOGIN'
  }
};

const logoutUser = () => {
  return {
    type: 'LOGOUT'
  }
};
```

9:03 -- The Vietnamese guy said he was usually doing 20-25 FreeCodeCamp exercises per day. I on the other hand thus far today have finished....... 1. Better keep at it!

9:07 -- Here are my notes for [exercise #7](https://learn.freecodecamp.org/front-end-libraries/redux/use-const-for-action-types) in FreeCodeCamp's Redux curriculm:

* It's common practice when working with Redux to assign action types as read-only constants.
* It's a general convention to write constants in all uppercase letters and this standard practice extends to Redux.

That exercise was easy enough:
```
// change code below this line
const LOGIN = "LOGIN"
const LOGOUT = "LOGOUT"
// change code above this line

const defaultState = {
  authenticated: false
};

const authReducer = (state = defaultState, action) => {

  switch (action.type) {

    case LOGIN:
      return {
        authenticated: true
      }

    case LOGOUT:
      return {
        authenticated: false
      }

    default:
      return state;

  }

};

const store = Redux.createStore(authReducer);

const loginUser = () => {
  return {
    type: LOGIN
  }
};

const logoutUser = () => {
  return {
    type: LOGOUT
  }
};
```

9:12 -- I'm going to take a break to do my morning routine (bathroom, brush teeth, etc). Then I'll come back and continue with exercise #8.
___
9:30 -- I'm back. Here are my notes for [exercise #8](https://learn.freecodecamp.org/front-end-libraries/redux/register-a-store-listener) in the FreeCodeCamp redux curriculm:

* store.subscribe() is another method we can use on the Redux *store* object.

* This allows us to subscibe listener functions to our store, having said functions called whenever an action is dispatched against the store (while I somewhat understand this idea intellectually,I'd have a difficult time explaining it to someone else).

Here is an example (that I wrote), of the code you'd need to write to pass this exercise:
```
  store.subscribe(() =>{
count++
  })
  ```
9:35 -- Here are my notes for [exercise #9](https://learn.freecodecamp.org/front-end-libraries/redux/combine-multiple-reducers) in the FreeCodeCamp Redux curriculm:

* The most fundamental principle of Redux is that all state is held in a single state object in the store.
* When your application grows more complex, you can use multiple reducers to handle different pieces of your application's state, and then compose (combine) these reducers into one root reducer.
* The most important reducer, and the one we pass in the Redux createStore() method is called the root reducer.
* If you'd like to combine multiple reducers, you can do so using the combineReducers() method.
* The combineReducers() method accepts an object as an argument. In this object you'll define properties which associate keys to specific reducer functions.
* It's typically good practice to create a reducer for each piece of application state that is distinct or unique in some way.

9:46 -- Here's an example (that I wrote) of using the combineReducers() method:
```
const rootReducer = Redux.combineReducers({
  count: counterReducer,
  auth: authReducer
})
```
9:47 -- We are now on [exercise #10](https://learn.freecodecamp.org/front-end-libraries/redux/send-action-data-to-the-store) of the FreeCodeCamp Redux curriculm. Here are my notes:
* The actions we dispatch to the Redux store will often contain a *type*, but we are not limited to only sending a type along with our actions. In fact, it is *very* common for us to also send data along with our actions.

10:07 -- That last exercise was a bit confusing, but I finally managed to solve it using the following code:
```
const ADD_NOTE = 'ADD_NOTE';

const notesReducer = (state = 'Initial State', action) => {
  switch(action.type) {
    // change code below this line
case ADD_NOTE:
return (action.text)
    // change code above this line
    default:
      return state;
  }
};

const addNoteText = (note) => {
  // change code below this line
return {
  type: ADD_NOTE, 
  text: note
}
  // change code above this line
};

const store = Redux.createStore(notesReducer);

console.log(store.getState());
store.dispatch(addNoteText('Hello!'));
console.log(store.getState());
```
10:08 -- Anyway, I need to move apartments now. On the bright side, I've already got more than 50% of my practice time in from yesterday. Today will be better!
___
**Total time spent coding today**: 

**Total time spent coding  thus far in June 2019**: 

**Total lifetime hours of coding**: 

