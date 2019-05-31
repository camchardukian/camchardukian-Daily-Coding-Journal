# Friday May 31st, 2019 Daily Coding Journal

15:21 -- Off to a bit of a late start today. Crazy that today is already the last day of May!

15:30 -- Here's something cool I just read from a FreeCodeCamp exercise. 

Not only is it possible to pass data to a child component, but it's also possible to take our handle or any other functions defined on the parent component and pass them onto a child component.

15:48 -- Just finished reviewing props. Now reviewing some of the different lifecycle methods.

15:50 -- Here's something interesting... 
> "React provides a synthetic event system which wraps the native event system present in browsers. This means that the synthetic event system behaves exactly the same regardless of the user's browser - even if the native events may behave differently between different browsers" -- [FreeCodeCamp](https://learn.freecodecamp.org/front-end-libraries/react/add-event-listeners)

15:56 -- FreeCodeCamp started talking about keyboard events in passing. I didn't fully grasp what they were talking about. Watching [a video on keyboard events](https://www.youtube.com/watch?v=5-koI06rmcA) now.

15:58 -- Here are three types of keyboard events we may find ourselves using in the browser:
1. **keydown** -- Activated when you touch a key.
1. **keyup** -- Activated when you release a key.
1. **keypress** -- Activated after you touch AND release a key.

16:00 -- Generally speaking, regardless of what order you wrote your code in you'll typically find keyboard events typically triggered in the same order as listed above (keydown, keyup, keypress).

Obviously, this is because it's impossible to release a key before you touch it. And... it's impossible to touch and release a key before it's released.

16:13 -- Here's some code I just finished writing:
```
  componentDidMount() {
document.addEventListener('keydown', this.handleKeyPress)
  }
  componentWillUnmount() {
document.removeEventListener('keydown', this.handleKeyPress)
  }
```
While I have a surface level understanding of the concept of keydown, keyup, and keypress, I'm definitely not super comfortable with them yet.

I'm sure that'll just require more exposure as they don't seem that complex :)

16:15 -- I'm feeling tired. I think I need more sunlight. I haven't gotten enough these last few days.

I just set a 35 minute timer. I'm going to commit this journal to GitHub, stretch, walk to another convenience store, and get back to programming before time is up.
___
16:41 -- I'm back. 

16:48 -- This React material on FreeCodeCamp is just *too* dull. I'm going to move on to learning Redux and go back to FreeCodeCamp, or more likely Scrimba's *Learn React for Free* course if I need to review anything from React. 

16:50 -- Like Dylan Israel says, you've got to be introspective. When learning material is just too dry or unengaging, you've got to move to something different to ensure you come back to coding tomorrow.

16:51 -- I'm going to listen to and take notes on Traversy Media's [Redux Crash Course With React](https://www.youtube.com/watch?v=93p3LxR9xfM).

His markdown crash course was excellent so I'm expecting only the same from this one!

16:54 -- My notes from the video start below.

Based on the first two minutes, Brad makes it sound like setting up Redux is a pain, and that it isn't much fun to learn.

*Why learn Redux?*

Apparently it is very helpful, and almost mandatory when dealing with large React applications.

16:57 -- While in standalone React we get component level state, the implementation of Redux allows us to enjoy application level state.

16:59 -- Brad just explained a concept and said, 
>"Hopefully that didn't just confuse the shit out of you and turn you off of Redux forever."

This has me fired up to continue hahaha.

17:02 -- Anytime you want to share state between components... is a great opportunity for introducing Redux into your application.

17:13 -- Taking a 5-10 minute break to restore focus.

___
17:25 -- 20 minutes into the video and he hasn't shown any Redux example implementations or done anything beyond merely discuss React Basics O_O.

17:32 -- I'm giving up on that tutorial for now. I got almost nothing out of it. I felt like he just programmed in React normally without explaining why he was doing anything.

17:33 -- I'm going to try watching this [Redux Fundamentals](https://www.youtube.com/watch?v=0ix_QLPkYhI) video instead.

17:34 -- To install redux we can use the following command in our terminal:
```
npm install redux --save
```

17:36 -- If you want to create a Redux app or convert your existing application into Redux there are four steps you should follow:
>#1 Create a Store

It's important to note that creating a store requires two pieces of information from the developer -- A reducer, and a state (Hopefully we'll get an explanation of what this actually means later).

>#2 Create a Reducer
       
Creating a reducer requires that we have two things -- state and an action.

>#3 Subscribe

In the video Hitesh says that subscribe basically just means to get the current state.

>#4 Dispatch

Dispatch is basically the action that we need to take.

17:50 -- Here's some example syntax of creating a store from the video.
``` 
const store = createStore(reducer), "Peace"
```
17:52 -- When I come back later, I'll finish Hitesh's video and go through the other steps in Redux.
___
22:34 -- I'm going to try to get a quick 25 minute practice session before getting on a call with a recruiter.

22:35 -- Now let's talk about the reducer. Here's some of the basic syntax:
```
const reducer = function(state, action) {

}
```
The above could also be written using arrow function syntax.

22:38 -- Here's a more complete example of the reducer syntax from Hitesh's video:
```
const reducer = function(state, action) {
    if(action.type === "ATTACK") {
        return action.payload
    }
}
```

22:40 -- Here's some example syntax from the subscribe step:
```
store.subscribe(() => {
    console.log("Store is now", store.getState())
})
```
If I'm being perfectly transparent, I do not fully understand why all of these steps are necessary.

22:43 -- Next, moving onto dispatch... Dispatch is usually an object.

22:44 -- Here's Hitesh's example syntax for dispatch:

```
store.dispatch({type: "ATTACK", payload: "Iron Man"})
```

22:48 -- It seems reducer, and dispatch must be put into their own separate files.

22:52 -- Another important thing to note is that despite being step #2, reducer should still be listed at the top of your code (clarification: written first amongst the 4 redux steps we discussed.)

22:54 -- I finished Hitesh's video. Now I'm going to commit this to Github, and then get ready for the recruiter meeting at 11.

___
**Total time spent coding today**: 

**Total time spent coding thus far in May 2019**: 


**Total lifetime hours of coding**: 

