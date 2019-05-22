# Wednesday May 22nd, 2019 Daily Coding Journal

8:46 -- Here's the plan:
1. Watch the forms tutorial again.
1. Copy the forms code by hand 3 times.
1. Watch the forms tutorial a third time.
1. Take a short break.

Let's go!


8:56 -- I just finished watching [the tutorial](https://scrimba.com/p/p7P5Hd/cW8Jdfy), now I'm going to practice writing the code by hand.

9:10 -- I've finished writing the code by hand twice now, but my neck is starting to get sore so I'm going to take a 5 minute break.

9:17 -- I'm back. Let's continue writing.

9:23 -- I'm going to write it a 4th time.

9:29 -- Now I'll watch the tutorial one more time, and see if I can do anything on my own (not feeling confident thus far).

9:35 -- I'm not feeling very motivated today. I strongly considered concluding this pomodoro session now, but I'm going to push forward at least another 10-15 minutes to build character.

9:44 -- Building from scratch... Here's what I've gotten thus far:

```
import React from "react"

class App extends React.Component {
    constructor () {
        super()
        this.state = {
            firstName: "",
            lastName: ""
        }
    }
    
    handleChange () {
        console.log("hello")
    }
    
    render () {
        return (
        <form>
        <input type ="text" placeholder = "first name here" onChange = {this.handleChange}/> 
        </form>
        )
    }
}

export default App
```

9:45 -- Notice that I didn't yet add this.handleChange = this.handleChange.bind(this) inside of the constructor yet. 

This is because it isn't technically necessary at this time as I haven't yet used the setState() method in any of my class methods.

Once I begin using the setState() method inside of my handleChange class method, however, I'll then have to begin using bind.

9:48 -- Here's where I'm at now:

```
import React from "react"

class App extends React.Component {
    constructor () {
        super()
        this.state = {
            firstName: "",
            lastName: ""
        }
        this.handleChange = this.handleChange.bind(this)
    }
    
    handleChange () {
        this.setState({
            firstName: event.target.value
        })
    }
    
    render () {
        return (
            <div>
        <form>
        <input type ="text" placeholder = "first name here" onChange = {this.handleChange}/> 
        </form>
        <h2> {this.state.firstName} </h2>
        </div>
        )
    }
}

export default App
```

9:51 -- Something isn't write as the code inside of my h2 tags isn't rendering to the screen as I intended. I'll try to figure out what's going on in the next pomodoro session.

23:32 -- Relaxed with my girl and began dealing with some complex fiscal issues today. Will try to get back on track with coding tomorrow.
___
**Total time spent coding today**: 1 hour 10 minutes
___
**Total time spent coding thus far in May 2019**: 53 hours 45 minutes

**Total lifetime hours of coding**: 549 hours 39 minutes