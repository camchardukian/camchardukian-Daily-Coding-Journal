# Thursday May 30th, 2019 Daily Coding Journal

10:44 -- I went to sleep at about 3:30am. Right now I'm running on about 5.5 hours of sleep. It's not ideal, but I'm trying to get out of my week-long habit of staying up until 3am each day. Anyway, on to FreeCodeCamp we go!

10:47 -- 
>"The way to override the default props [(that you've set in React)] is to explicitly set the prop values for a component." -- FreeCodeCamp

Seems reasonable enough.

10:53 -- Check it out, here's some good information. In React we have access to something called type-checking features.

These allow us to mandate that the data of our prop be of only a specific type.

For example, if we know an API call should retrieve data in the form of an array we can require our component to only accept said data if it is in the form of an array.

If the data is of any other type, it will be rejected.

11:03 -- It looks like when using ES6 class components we may need to use the *this* keyword when accessing props, whereas appears to be unnecessary when accessing props in functional components.

11:08 -- SO tired lol. I'm going to commit this to GitHub and then take a mini nap at this convenience store.

I WILL NOT leave the convenience store because that would make it too easy to stop coding.

When my nap is finished I'll continue coding.
___
11:41 -- I just spent 10ish minutes cleaning up some space on my hard drive, 3ish minutes commiting this journal to GitHub, and another 10-15 minutes taking a quick nap. Now let's get back to FreeCodeCamp!

11:52 -- It's not easy coding on 5.5 hours of sleep, but I'm getting along. I finished up with stateless components (at least for now), and am now going through FreeCodeCamp's exercises on stateful components.

12:00 -- I recognize already that this is a huge feature of React, but I don't think I fully yet grasp the entire magnitude of it:
>"React updates the actual DOM, but only where necessary. This means you don't have to worry about changing the DOM. You simply declare what the UI should look like." -- FreeCodeCamp

12:01 -- Here's another nice idea I picked up from from [the exercise I'm currently working on](https://learn.freecodecamp.org/front-end-libraries/react/render-state-in-the-user-interface).

State is completely encapsulated. This means that it is local to only the component in which it was declared.

Components can't "see" the state inside of other components in our application unless we pass state data to child components as props.

12:06 -- Quick note to anyone actually going through these React exercises on FreeCodeCamp.

If you're finding yourself unable to pass FCC's tests for a seemingly unknown reason, try to go back to your code and delete any unnecessary spaces. 

While it's possible there's something wrong with your logic, I've found that often the issue is unnessary spaces have the potential to trip up FreeCodeCamp's verification tests.

While it would probably be a bit of a timesuck to develop, I believe FCC could improve the functionality of their tests by implementing RegEx and instead of searching for exact matches in the code, allow for the possibility of an exact match that has an unknown number of spaces (though not other impermissable characters) at either the beginning or end of the match.

Perhaps I am oversimplifying things, but this seems like it would be something FCC could look into. Anyway, back to the FCC exercises!

12:13 -- React may batch multiple state updates in order to improve performance.

12:19 -- I'm burnt. I'm going to get lunch, take a nap, and get a few more pomodoro sessions in later!
___
**Total time spent coding today**: 

**Total time spent coding thus far in May 2019**: 

**Total lifetime hours of coding**: 

