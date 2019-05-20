# Monday May 20th, 2019 Daily Coding Journal

8:45 -- Here we are. Another day another dollar. Or 100 dollars in the future after I've developed my skills haha. Let's get to work!

8:47 -- I'm going to rebuild yesterday's[conditional rendering practice exercise](https://scrimba.com/p/p7P5Hd/c893vh2) from scratch to review and condense everything I've learned. Then, later in the day I'll continue to the next video in the course. Let's see if I can build this project without getting *any* hints from the course instructor.

8:58 -- For a minute or two I was hung up on why my clickHandle function wasn't able to toggle the state. I was wondering why *this.state.isLoggedIn* was always set to true despite my attempts to set it to equal the opposite of whatever *prevState.isLoggedIn* was set to.

It turns out my oversight was very simple. I forgot to return the value of the callback function. And yes... I figured this out on my own without needing to consult the tutorial! :D

9:08 -- I've completed everything! Here's my code:
```
import React from "react"

class App extends React.Component {
    constructor() {
        super()
        this.state = {
            isLoggedIn: true
        }
        this.handleClick = this.handleClick.bind(this)
    } // closing bracket for constructor
    
    handleClick () {
        this.setState(prevState => {
            return (
            {isLoggedIn: !prevState.isLoggedIn}
            )
        })
    }
    
    
    render () {
        let buttonText;
        let statusText;
        this.state.isLoggedIn ? buttonText = "log out" : buttonText = "log in"
        this.state.isLoggedIn ? statusText = "You are currently logged in" : statusText = "You are currently logged out"
        return (
        <div>
            <button onClick = {this.handleClick} >{buttonText} </button>
            <h2> {statusText} </h2>
        </div>
        )
    }
    
} // closing bracket for app component

export default App
```
9:09 -- In retrospect, I do feel that if this was a commercial production that it may be useful to take the ternary operators and variables from my render method and stick them into their own Conditional.js component. This would likely make my code more readable. For now, however, we shall trudge onwards!

9:12 -- The [next video](https://scrimba.com/p/p7P5Hd/cKe27SD) in the course wants us to take the items that have already been completed, and style those items differently. To be honest, I I'm going to have to go and review how React and CSS work together. It's been a long time since that concept was introduced.

9:24 -- I've spent the last 10 minutes or so reviewing how I can use CSS with React, and how to style properties in my application.

I'm going to go for a walk now, and pick up breakfast/lunch before the Bun Thit Nuong restaurant closes. 

When I come back I'll try to apply what I've learned about using CSS in React to styling elements based on what their state is currently set to.
___
**Total time spent coding today**: N/A
___
**Total time spent coding thus far in May 2019**: N/A
___
**Total lifetime hours of coding**: N/A