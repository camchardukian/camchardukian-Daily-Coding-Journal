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
14:42 -- I finished moving into my new apartment now. I still need to clean things up a bit, but it feels good to have settled that... at least temporarily.

Let's get back to FreeCodeCamp!

14:43 -- I thought I was on exercise #11, but it looks like I miscounted or forgot to take notes on one of the exercises. 

Anyway, we're continuing with [exercise #12 Use Middleware to Handle Asynchronous Actions]() in the FreeCodeCamp Redux curriculm. :D

Here are my notes from this exercise:
* Asynchronous actions are an unavoidable part of web development.

* We can use Redux Thunk middleware to deal with ocassions in which we need to call asynchronous endpoints in our Redux application.

* To include Redux Thunk  middleware in our project, we pass it (usually in the form of ReduxThunk.default) as an argument to *Redux.applyMiddleWare()*.

* Of course, it's also important for us to make sure we can actually access *Redux.applyMiddleWare*. We can do that by including Redux.applyMiddleWare() as an optional second parameter to the createStore() function.

14:59 -- Overall, I don't really know much about asynchronous programming.

I'm going to explore this concept in general before I proceed with trying to finish this challenge.

15:01 -- Going off of some videos I just watched on YouTube, it looks like synchronous programs are those where the code runs completely in chronological order.

In other words, if something in the code gets stuck, or requires a long time to load or process something, the process of having the program's logic evaluated will come to a halt.

On the other hand, asynchronous programming is useful because let's say we make an API call to a server that is currently being overloaded.

In our program we can specify that in a situation such as this, we want the rest of our program to continue running even while the API call is being made.

15:09 -- While I'm inexperienced with asynchronous programming myself (I remember having used some promises in my React projects for example), I now understand the general concept of it, and why we would want to program asynchronously.

15:11 -- I'm going to take a bit of a break now to do some work on another project.
___

16:00 -- I'm back, let's get another short pomodoro in.

16:06 -- I'm currently watching a [Techsith video on Redux MiddleWare](https://www.youtube.com/watch?v=grZ4BVcFmeA).

16:14 -- I didn't get much from that video. I guess I'll just go back to the FreeCodeCamp exercise and try to figure things out for myself.

16:20 -- Got nowhere with my first attempt to pass the challenge:
```
dispatch requestingData()
```
I need to go relearn how to dispatch actions using Redux.

16:32 -- I'm so lost beyond lost. I've watched several videos on this topic and everything seems to be going straight over my head.

I'm going to take a break to go to the supermarket, and then I'll try to come back with a fresh perspective later.
___
21:24 -- I'm going to try to get another 20-40 minutes of programming in before I call it a day.

 Apart from actual "coding" today, I've also begun putting together my web developer resume.

 Of course, building a resume doesn't contribute to my "total time spent coding" I'll talk about at the end of today's entry.
 
 So... let's get back to coding!

 21:26 -- I've been getting really frustrated with Redux so I'm going to try working on another project.

 21:48 -- Could not get React running properly on Codepen nor could I use the reactboilerplate application without running into errors. 

 21:49 -- I am so frustrated.

 21:52 -- Tomorrow I'll either go back to learning Redux, or try to setup my own React app by following some tutorial. Maybe [this one](https://www.tutorialspoint.com/reactjs/reactjs_environment_setup.htm) for example.
___
**Total time spent coding today**: 2 hours 50 minutes

**Total time spent coding  thus far in June 2019**: 
6 hours 55 minutes

**Total lifetime hours of coding**: 577 hours 38 minutes

