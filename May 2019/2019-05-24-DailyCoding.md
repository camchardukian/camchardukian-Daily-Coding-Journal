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
20:55 -- Let's continue the hustle. I'll build the form from scratch to prove I can replicate my success, and then I'll move on to the [forms part II video](https://scrimba.com/p/p7P5Hd/cGKqZUQ).

21:07 -- I did it again. Here's my code:

```
import React from "react"

class App extends React.Component {
    constructor() {
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
            [name]: value
        })
    }
    
    render () {
        return (
        <form>
        <input type = "text" placeholder = "First Name" value = {this.state.firstName} name="firstName" onChange = {this.handleChange} />
        
        <br/>
        
        <input type = "text" placeholder = "Last Name" value = {this.state.lastName} name="lastName" onChange = {this.handleChange} / >
        <h1> {this.state.firstName} {this.state.lastName} </h1>
        </form>
    )
    }
}

export default App
```

21:08 -- I can now make forms that utilize text inputs with React. Let's learn more about other types of form inputs now. I'll watch the Forms Part II video all the way through first, and then I'll take notes.

21:20 -- Wow, that video was pretty dense. I'm going to take a 5 minute break to go to the bathroom, and stretch. Then I'll take notes on it.
___
21:26 -- I'm back. The following notes are from [this video](https://scrimba.com/p/p7P5Hd/cGKqZUQ).

* In HTML 5 the textarea element is different than the input element in that the input element is a self-closing element while the textarea element has a closing tag. In React, however, **both** are self-closing elements.

* Because the textarea tag has been slightly modified in React (versus HTML) the textarea element is now compatible with the value property. This is useful because it allows us to set or modify the default text inside of our textarea element using state.

* We do *not* use the value property with checkboxes.

* The checkbox DOES, however utilize a checked property. This checked property will usually rely on the value of state being set to a boolean. If state is set to *true*, the checkbox will be checked.

* Our handleChange method looks at the value property of our text inputs. This is not the case with checkboxes, however, because checkboxes don't have a value property.

* Building off the previous note, it's important to understand the power of event.target within our handleChange method. Using event.target, we can pull out the type and checked properties of any elements that our onChange event handler and handleChange method are being applied to.

* Because checkboxes and text inputs utilize the setState function with different properties, it is necessary for us to use a ternary operator in order to decide whether we are going to setState for an element based on a text input element procedure or a checkbox element procedure.

* Radio buttons have  both a value property and a checked property.

* By giving the same name to all of your radio buttons, you ensure that the user can only select one option at a time.

* The select element has also incorporated the value property in React.

* The course instructor stresses that it isn't necessary to remember the syntax for all of these different form elements. It's perfectly ok to rewatch this video, or look up old code you've written as you're learning. Over time you'll acquire muscle memory on the correct syntax and find yourself being able to do things from memory or off the top of your head easier and easier.

* In HTML, when buttons are nexted within a form and clicked they will serve as a submit button for the form.

21:53 -- I've finished the video. Tomorrow I'll write all of the code by hand once or twice to get it into my muscle memory. Then I'll see if I can reconstruct some of the different types of forms from scratch.

21:54 -- On a quick side note, today was OK. I got a couple hours of programming in, but I feel as if I'm not pushing myself enough. **I need to GO ALL IN on code**.


___
**Total time spent coding today**: 2 hours 34 minutes

**Total time spent coding thus far in May 2019**: 56 hours 54 minutes

**Total lifetime hours of coding**: 552 hours 48 minutes