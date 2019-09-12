# Thursday September 11th, 2019 Daily Coding Journal

20:24 -- Here's what my day at the office looked like today:
```
7:50 - 8:00
Connected keyboard

Connected mouse

8:00 - 11:10

Caught up on Chatwork/email

Reviewed Redux flow while waiting for pull request to get reviewed.

Refactored code, and made new pull request.

11:10 - 11:45
Reviewed source code and looked into which APIs will be necessary for the next task.

11:45 - 12:45
Lunch

12:45 - 5:10
Worked on new page displaying friends/connections
Reviewed API docs
```
20:26 — I watched one of Chris Sean’s videos yesterday. In the [video](https://www.youtube.com/watch?v=wA50nSW1l-U), there was some advice for junior developers. One of Chris Sean’s coworkers or someone he knew said,
```
“Do not go a day without practicing an area you feel weak in, whether its going over that code you need to refactor, an improved algorithm or a new quicker tool.

Practice, practice and practice some more, but not what you already know, only you can feel what you are bad at or how you can improve an existing situation.

Practice with a defined intention, be motivated even if it takes day or weeks, enjoy struggling and focus on the outcome. Decide what is a pain and what the perfect outcome will be. Work like a dog at 4am, skip lunch to cover more or spend time on the weekend doing it, get yourself alleviated.”
```

20:32 — I really like this quote, and I’m going to apply it by \**drum roll*\* studying Redux. Every. single. day. At least, until my team lead says that I’m good at Redux.

20:33 — Tonight I’m watching a video about Redux for beginners. The video creator says that in React, data can only flow downwards using props.

This may be fine for small applications, but things can quickly get messy when we work with larger applications. That’s basically the gist of why Redux is popular.

20:36 — The store holds all of the state/data in our application.

20:37 — In redux, an action is basically the thing we want to do. In a counter app for example, our action would be called “Increment”.

20:39 — Our reducer basically describes how our action will modify our state.

20:40 — Actions get sent or “dispatched” to the reducer.

20:41 — An action is a function that returns an object.

20:44 — Based on the name of the action, the reducer knows how to modify state.

20:48 — It’s only possible to pass a single reducer into the Redux store. For that reason, Redux has a concept called *combineReducers* which is basically a const variable or function that will combine all of our reducers into one variable to pass into ourRedux store.

20:54 — We import *Provider* from ‘react-redux’.  We then wrap our entire App (typically in the App.js or index.js file) inside of our Provider tag.

Here’s some example code:
```
ReactDOM.render(
<Provider store={yourStoreNameHere}>
<App />,
document.getElementById(‘root’)
);
```

20:59 — We need to import *useDispatch* fro ‘react-redux’ in order to obtain the ability to dispatch actions.

21:11 -- Time to get dinner, and maybe exercise a little before bed!
___
**Total time spent working as an employed developer today**: 8 hours 3 minutes

**Total time spent practicing code outside of work today**: 50 minutes

**Total time spent practicing code outside of work thus far in September 2019**: 17 hours 6 minutes

**Total lifetime hours practicing code outside of a job**: 717 hours 41 minutes

**Total lifetime hours working as an employed developer**: 131 hours 35 minutes