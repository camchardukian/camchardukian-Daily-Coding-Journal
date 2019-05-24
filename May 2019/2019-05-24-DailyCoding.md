# Friday May 24th, 2019 Daily Coding Journal

13:35 -- Here we go. Let's shoot for at least two hours of programming today.

13:47 -- I just finished watching the forms tutorial again. I'm going to practice writing code by hand and then try to rebuild the form from scratch.

14:01 -- I just finished writing the instructor's code by hand two times. Now I'm going to see how much I can build on my own.

14:13 -- Not sure what's up, but I can't figure out what I'm doing wrong when setting state. Here's my code:

```
import React from "react"

class App extends React.Component {
    constructor() {
        super()
        this.state = {
        firstName: "gfewfwer"
    }
    this.handleChange = this.handleChange.bind(this)
    }

handleChange () {
    console.log("ge")
    this.setState({
        ["firstName"] : event.target.firstName
    })
}

render () {
    return (
        <div>
        <form>
        <input type = "text" name="firstName" placeholder = "First Name" onChange = {this.handleChange}/>
        </form>
    <h1> {this.state.firstName} </h1>
    </div>
    )
}
}

export default App
```
I know my handleChange method is functioning because the console.log() method nested inside of it is working fine. There's just something I'm doing wrong in setting state...

14:17 -- The following code isn't working either O_O

```
import React from "react"

class App extends React.Component {
    constructor() {
        super()
        this.state = {
        firstName: "gfewfwer"
    }
    this.handleChange = this.handleChange.bind(this)
    }

handleChange () {

    this.setState({
        const {name, value} = event.target
        name : value
    })
}

render () {
    return (
        <div>
        <form>
        <input type = "text" name="firstName" value="this.state.firstName" placeholder = "First Name" onChange = {this.handleChange}/>
        </form>
    <h1> {this.state.firstName} </h1>
    </div>
    )
}
}


export default App
```

14:19 -- I'm going to take a quick walk now and try to get another 15 minutes or so of programming in before I have to attend to other obligations.
___
**Total time spent coding today**: N/A
___
**Total time spent coding thus far in May 2019**: N/A

**Total lifetime hours of coding**: N/A