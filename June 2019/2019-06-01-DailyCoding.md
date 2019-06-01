# Saturday June 1st, 2019 Daily Coding Journal

11:18 -- Here we go. I worked on another project outside of tech this morning, and now I'm going to try to get a quick pomodoro session in.

11:20 -- Today I'm going to go through [techsith's series on Redux](https://www.youtube.com/watch?v=7Erbf5NXQQw&list=PL7pEw9n3GkoWgIc-Ambc-QZGcTKEei2O3).

This series is a whopping 8 videos. I'll list the videos and some of the notes I took on each video below.

11:23 -- Here are some of my notes on video #1 -- [*Redux Introduction | How Redux works | Redux fundamentals*](https://www.youtube.com/watch?v=7Erbf5NXQQw)

* You may hate Redux if you don't understand it. Once you develop an understanding of it, however, it's quite simple and you will grow to love it.

* Redux is NOT part of React. It's a separate library that you can use with React (or any other JavaScript framework.)

* Global state is located in the store.

* The reducer holds functionality to modify the state.

* Redux can work in isolation. Using it doesn't require React.

11:33 -- That's the end of video one! I'm going to take a nap now, and we'll take notes on video #2 later!
___
14:41 -- I just got up from my nap. Let's get some more code in!

14:42 -- Here are my notes for [part II](https://www.youtube.com/watch?v=wZVzeob4ywc) of Techsith's series on Redux.

* The const variable is mutable but not replaceable. This means you can modify the value of const, but you cannot assign a value to const using "=" again.

* Whenever there is a change in state, the following code will automatically run.
```
store.subscribe(()  => {

}
```
* The value that we pass to an action is called the *payload*.

15:01 -- Here are my notes for [part III](https://www.youtube.com/watch?v=Fq15pkckMqQ) in Techsith's series on Redux.

* Using React's native functionality with state may be referred to as using local state while the implementation of Redux may lead to some developers referring to state as *Redux store state*.

* There are actually two packages we need when implementing Redux into a React project. The first is *Redux* itself, and then there is *React-Redux*. Here are the two commands we need to install them...
```
npm install redux -- save
```
```
npm install react-redux -- save
```

* Reducers are functions that take two arguments -- a state and an action.

* ES6 provided us with the ability to set default parameters.

* Our store has to be global.

* To connect React and Redux we need to use the following code:
```
import { connect } from 'react-redux'
```

15:27 -- I just finished part III. While I seem to be assimilating some of the knowledge contained in the videos, there's also definitely an aspect many would label as "imposter-syndrome".

Many of the notes I took contain concepts that I may not yet be able to fully explain. With that being said, while I still feel Redux is far from simple, I am beginning to see patterns and THAT is encouraging.

I'm going to take a break now, and continue with this series later.

___
**Total time spent coding today**: 

**Total time spent coding  thus far in June 2019**: 

**Total lifetime hours of coding**: 

