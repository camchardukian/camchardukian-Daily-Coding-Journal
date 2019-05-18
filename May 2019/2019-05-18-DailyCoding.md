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
20:02 -- I went for a walk, ate some fruit, listened to some computer science career videos and now we're back to the code. Scrimba was so kind as to refresh so now I have the opportunity to code everything again... from scratch. *Great!* lol O_O

20:09 -- I've gotten the basics setup.
```javascript
import React from "react"
import Conditional from "./Conditional"

class App extends React.Component {
    constructor() {
        super()
    }
    
    render() {
        return (
            <Conditional />
        );
    }
}


export default App

```

20:15 -- My code is a bit of a mess here:

```javascript
  componentDidMount({setTimeout(this.setState
    ) 
    }
    )
```
Let me go review this.setState so I can tidy things up.

20:27 -- Cleaned it up a little bit. But... still cannot figure out the syntax completely. I'm getting an error of unexpected token.
```
componentDidMount(setTimeout(this.setState({
        isLoading: false
    }) //closing bracket and parenthesis for setState
    ,1500) //time value, and closing parenthesis for setTimeout
    )
```

20:35 -- After spending 20 minutes trying to debug why the above code wasn't working I've finally figured it out. componentDidMount doesn't need to be taking setTimeout as a parameter. I should've included all of the above code in the function block of componentDidMount. Let me go grab the code and then I'll show you what I mean.

20:45 -- I've made some more progress, but I'm getting an issue where it says
>TypeError: Cannot read property 'isLoading' of undefined (/Conditional.js:14)

20:47 -- I'm going to go get dinner before everything closes. But... before I do that, I'm going to rewatch the tutorial from start to finish to pick up things I missed the first couple times through.

20:55 -- After watching like 30% of the video I was able to correct my code and get everything working. Here's my final code for this session.
**App.js...**

```
import React, {Component} from "react"
import Conditional from "./Conditional"

class App extends Component {
    constructor() {
        super()
        this.state = {
            isLoading: true
        }
    }
    
    componentDidMount() {
        setTimeout(() => {
            this.setState({
                isLoading: false
            })
        }, 1500)
    }
    
    render() {
        return (
            <div>
                <Conditional isLoading={this.state.isLoading}/>
            </div>
        )
    }
}

export default App
```
**Conditional.js:**
```
import React from "react"

function Conditional (props) {
    console.log(props.isLoading)
        if (props.isLoading) {
         return (
             <h1> Loading </h1>
         )   
        }
        else {
        return (
            <h1> Finished loading already </h1>
        )    
        }
}


export default Conditional
```
I know things aren't super clean now. There's some refactoring to be done. For example, I should have implemented a ternary operator in Conditional.js instead of using an *if else* statement in order to keep my code shorter. I'm pretty happy with this session overall though!

I'm going to take a break now to get dinner and be back for another session either tonight or tomorrow depending on time restraints.
___
23:30 -- I got dinner, called my mom, went through my night routine, and now it's time to get one more session of code in before bed.

23:38 -- I've done the basic setup of the app including:
* imports/exports
* constructor/super
* rendering

23:39 -- Now I'm going to implement a simulated API call using setTimeout and conditional rendering.

23:41 -- Getting close...
```
import React from "react"
import Conditional from "./Conditional"

class App extends React.Component {
    constructor () {
        super() 
        this.state = {
            isLoading: true
        }
    }
    
    render() {
        console.log(this.state.isLoading)
        return (
        <Conditional isLoading={this.state.isLoading} />
        )
    }
}
```

23:47 -- Ohhh my baby here is looking puuuurty:
```
 componentDidMount() {
    setTimeout(() => this.setState({
    isLoading: false    
    }), 2000)
    }
```

23:48 -- Now I'm going to try to write the conditional statement inside of Conditional.js. I'll first do the logic using an if else statement and then refactor it using a ternary for brevity.

23:55 -- My application is now functional! Here's the example code from my **Functional.js file:**

```
import React from "react"

function Conditional (props) {
if (props.isLoading) {
    return (
        <h1>Please wait for your data to be fetched... </h1>
    )
}
    return (
        <h1> Example data from API call here </h1>
    )
}

export default Conditional
```

23:56 -- Now let's do it again using a ternary operator...

23:59 -- I've finished. To see the final output look in daily coding journal entry 2019-05-18...
___
**Total time spent coding today**: 3 hours 15 minutes
___
**Total time spent coding thus far in May 2019**: 38 hours 57 minutes
___
**Total lifetime hours of coding**: 534 hours 52 minutes