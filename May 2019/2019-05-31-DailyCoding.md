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
continue here...
___
**Total time spent coding today**: 

**Total time spent coding thus far in May 2019**: 


**Total lifetime hours of coding**: 

