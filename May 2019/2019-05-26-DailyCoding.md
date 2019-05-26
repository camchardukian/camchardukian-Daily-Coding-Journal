# Sunday May 26th, 2019 Daily Coding Journal

18:20 -- Off to a bit of a late start today. Had about 4 hours of other work projects, and caught up on some sleep. Now let's get some code in.

18:26 -- I've started working on the [following exercise(https://coursework.vschool.io/travel-form/)] on building forms. Of course, I've adapted the exercise a bit to complete it in React rather than Vanilla JS.

18:39 -- So, the challenge was to finish a partially filled airline form. I haven't finished yet, but here's a quick update on my progress after 10 minutes or so:

```
import React, {Component} from "react"

/**
 * Challenge: Wire up the partially-finished travel form so that it works!
 * Remember to use the concept of controlled forms
 * https://reactjs.org/docs/forms.html
 * 
 * All information should be populating the text below the form in real-time
 * as you're filling it out
 * 
 * This exercise is adapted from the V School curriculum on vanilla JS forms:
 * https://coursework.vschool.io/travel-form/
 * 
 * All of our challenges and learning resources are open for the public
 * to play around with and learn from at https://coursework.vschool.io
 */

class App extends Component {
    constructor() {
        super()
        this.state = {
            firstName: "",
            lastName: "",
            age: null
        }
        this.handleChange = this.handleChange.bind(this)
    }
    
    handleChange (event) {
        const {name, value, type, checked} = event.target
        console.log("hello")
        this.setState ({
            [name]: value
        })
    }
    
    render() {
        return (
            <main>
                <form>
                    <input placeholder="First Name" name="firstName" onChange = {this.handleChange} /><br />
                    <input placeholder="Last Name" name="lastName" onChange = {this.handleChange} /><br />
                    <input placeholder="Age" name="age" onChange = {this.handleChange} /><br />
                    
                    {/* Create radio buttons for gender here */}
                    <br />
                    
                    {/* Create select box for location here */}
                    <br />
                    
                    {/* Create check boxes for dietary restrictions here */}
                    <br />
                    
                    <button>Submit</button>
                </form>
                <hr />
                <h2>Entered information:</h2>
                <p>Your name: {this.state.firstName} {this.state.lastName}</p>
                <p>Your age: {this.state.age} </p>
                <p>Your gender: {/* Gender here */}</p>
                <p>Your destination: {/* Destination here */}</p>
                <p>
                    Your dietary restrictions: 
                    {/* Dietary restrictions here, comma separated */}
                </p>
            </main>
        )
    }
}

export default App
```

18:49 -- I'm having some issues getting my radio buttons to work properly. Here's where I'm at right now...

```
<label> Gender: </label>
<br />
<input type = "radio" name = "male" value = {this.state.gender === "male"} onChange = {this.handleChange} /> Male
<br />
<input type = "radio" name = "female" value = {this.state.gender === "female"} onChange = {this.handleChange} /> Female
<br />
<input type = "radio" name = "other" value = {this.state.gender === "other"} onChange = {this.handleChange} /> Other
```
The above code gets the radio buttons to display properly, but once selected I cannot unselect the radio buttons. In addition, I'm able to select more than one radio button at once which obviously isn't what we're intending to do with radio buttons.

18:53 -- As I suspected, the issue is that I gave all of my radio buttons different names. They should all have the same name so that only one is able to be selected at a time.

18:59 -- I've completed name, age, and gender on my form thus far:

```
import React, {Component} from "react"

/**
 * Challenge: Wire up the partially-finished travel form so that it works!
 * Remember to use the concept of controlled forms
 * https://reactjs.org/docs/forms.html
 * 
 * All information should be populating the text below the form in real-time
 * as you're filling it out
 * 
 * This exercise is adapted from the V School curriculum on vanilla JS forms:
 * https://coursework.vschool.io/travel-form/
 * 
 * All of our challenges and learning resources are open for the public
 * to play around with and learn from at https://coursework.vschool.io
 */

class App extends Component {
    constructor() {
        super()
        this.state = {
            firstName: "",
            lastName: "",
            age: null,
            gender: ""
        }
        this.handleChange = this.handleChange.bind(this)
    }
    
    handleChange (event) {
        const {name, value, type, checked} = event.target
        console.log("hello")
        this.setState ({
            [name]: value
        })
    }
    
    render() {
        return (
            <main>
                <form>
                    <input type = "text" placeholder="First Name" name="firstName" onChange = {this.handleChange} /><br />
                    <input type = "text" placeholder="Last Name" name="lastName" onChange = {this.handleChange} /><br />
                    <input type = "text" placeholder="Age" name="age" onChange = {this.handleChange} />
                    <br />
                    <label> Gender: </label>
                    <br />
                    <input type = "radio" name = "gender" value = "male" checked = {this.state.gender === "male"} onChange = {this.handleChange} /> Male
                    <br />
                    <input type = "radio" name = "gender" value = "female" checked = {this.state.gender === "female"} onChange = {this.handleChange} /> Female
                    <br />
                    <input type = "radio" name = "gender" value = "other" checked = {this.state.gender === "other"} onChange = {this.handleChange} /> Other

                    <br />
                    
                    {/* Create select box for location here */}
                    <br />
                    
                    {/* Create check boxes for dietary restrictions here */}
                    <br />
                    
                    <button>Submit</button>
                </form>
                <hr />
                <h2>Entered information:</h2>
                <p>Your name: {this.state.firstName} {this.state.lastName}</p>
                <p>Your age: {this.state.age} </p>
                <p>Your gender: {this.state.gender}</p>
                <p>Your destination: {/* Destination here */}</p>
                <p>
                    Your dietary restrictions: 
                    {/* Dietary restrictions here, comma separated */}
                </p>
            </main>
        )
    }
}

export default App

```

19:00 -- Later I'll finish the destination (select) and dietary restrictions (checkbox) part of the form.

23:56 -- I just finished exercising and recording a video for the daily developer channel. Obviously I'm going to have to get to finishing the forms tomorrow.


___
**Total time spent coding today**: 46 minutes

**Total time spent coding thus far in May 2019**: 60 hours 1 minute

**Total lifetime hours of coding**: 555 hours 55 minutes

