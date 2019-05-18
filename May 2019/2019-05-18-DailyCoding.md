# Saturday May 18th, 2019 Daily Coding Journal
13:58 -- We're off to a bit of a late start today due to other obligations, but no worries. We're still going to execute and put our time in.

14:02 -- When a functional component is rerendered, it basically means simply that the functional component will run (or be called) again.

14:05 -- The essence of conditional rendering is that we choose whether to render something or what to render to the screen based on if some condition evaluates to true.

14:08 -- A little more than halfway through [the video](https://scrimba.com/p/p7P5Hd/c4kJNSL) Bob Ziroll explains that it's a very common practice to use ternary operators with conditonal rendering.

14:12 -- Remember that if something is nested within a JSX element and we want that nexted something to be interpreted as JavaScript (rather than JSX), it's crucial for us to remember to enclose our JavaScript inside of curly braces.

14:14 -- Something to keep in mind is that we don't have to render all of our page simultaneously. In fact, I'd argue that most of the elements on an average webpage are static with only one or a few elements reliant on conditional rendering (if any).

14:18 -- It was an early morning so I'm feeling pretty drowsy now. I'm going to take a nap and maybe practice writing code by hand,and/or building the tutorial application from scratch when I come back.
___
15:48 -- Here we go, back on the grind.

18:11 -- I just spent the last 20 or so minutes rewriting the instructor's conditional rendering code by hand several times. I like to do this to help myself internalize syntax, and coding patterns.

18:16 -- I just got back from the bathroom. Now I'll try to rewrite the instructor's code that utilizes conditional rendering from scratch (or create my own similar solution).

18:27 -- Oh man, this is proving to be more difficult than I thought. It seems there's a lot of stuff I'm rusty on from the previous lessons in the course.

18:33 -- I'm making some decent progress:

```
import React from "react"
import Conditional from "./Conditional"

class App extends React.Component {
    constructor() {
        super()
        this.state = {
            isLoading : true
        }
    }
}

componentDidMount()
```
With that being said, I need quickly go review the syntax for the componentDidMount() lifecycle method before continuing.

18:37 -- [This video](https://www.youtube.com/watch?v=uMtK7f0TVq4) says that the componentDidMount() lifecycle method is called immediately after the render() method fires and everything is added to the DOM. According to React, it's usually a good idea to load in any external data from within the componentDidMount() method.

18:43 -- Now I'm trying to reimplement the setTimeout() method that's nested within the componentDidMount() method and intended to simulate and API call. Here's my current progress...

```
componentDidMount () {
    setTimeout(=> {
        
    }, 1500
    )
}
```
18:44 -- I'm going to go review the Beau Carnes setTimeout() video to see how I should go about doing this.

18:51 -- I'm feeling lost about how I should implement setTimeout() and componentDidMount() together. I'm stuck...
```
componentDidMount () {
    setTimeout((console.log("hello"), 1500)
}
```

18:52 -- I'm going to watch the [original tutorial](https://scrimba.com/p/p7P5Hd/c4kJNSL) all the way through, commit what I need to do to memory, take a walk, and then see if I can still implement the things that still require implementation.

18:54 -- Within 15 seconds of watching the video it's already immediately clear to me how I went wrong.
> I should have used this.setState along with changing the state of isLoading to false.

19:02 -- I'm going to go for a walk now, maybe eat some dinner, and then I'm going to get back to work.

___
**Total time spent coding today**: N/A
___
**Total time spent coding thus far in May 2019**: N/A
___
**Total lifetime hours of coding**: N/A