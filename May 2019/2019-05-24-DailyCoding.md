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

14:53 -- Walk took longer than expected, will do more work later.
___
19:41 -- I'm back. Let's put in another strong session and strengthen our knowledge of forms.

19:44 -- Now that I can finish setting up my React app and completing the form 90% from scratch, I'm not going to bother writing everything from scratch anymore. Now I'm going to focus on trying to solve the problem from scratch, and just copying by hand concepts that I need more time and exposure to for the internalization process.

20:22 -- I've finally done it. I've created the entire form from scratch! There were a few hiccups (such as when I couldn't figure out why the form wasn't working only to realize the problem was that I forgot to give my text inputs a relevant name property).

Overall though, my persistence has definitely increased my comfort in working with forms. While I cannot put the following code in a portfolio by itself, working through this problem makes me confident I'll be able to incorporate forms into any React projects I do add to my portfolio:

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
    
    handleChange (event) {
        const {name, value} = event.target
        this.setState({
            [name] : value
        })
    }
    
    render () {
        return (
        <form>
        <input type = "text" value = {this.state.firstName} name = "firstName" placeholder = "First Name" onChange = {this.handleChange} />
        <br/>
        <input type = "text" value = {this.state.lastName} name = "lastName" placeholder = "Last Name" onChange = {this.handleChange} />
        <h1> {this.state.firstName} {this.state.lastName} </h1>
        </form>
        )
    }
}

export default App
```

20:26 -- I'm going to take a walk and then I'll do some more programming.
___
**Total time spent coding today**: N/A

**Total time spent coding thus far in May 2019**: N/A

**Total lifetime hours of coding**: N/A