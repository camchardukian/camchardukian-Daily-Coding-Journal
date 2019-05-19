# Sunday May 19th, 2019 Daily Coding Journal

0:11 -- Wow, rarely do we start these daily coding journal entries so early.

Anyway, I said in yesterday's entry that we'd start today's entry with the code that I put together to practice conditional rendering.

Without any further ado, here it is...

**App.js**
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
    
    componentDidMount() {
    setTimeout(() => this.setState({
    isLoading: false    
    }), 2000)
    }
    
    render() {
        console.log(this.state.isLoading)
        return (
        <Conditional isLoading={this.state.isLoading} />
        )
    }
}

export default App
```
Conditional.js
```
import React from "react"

function Conditional (props) {
    return (
        <div>
        <nav> My navbar is here </nav>
{props.isLoading ? <h1> The data is being fetched... </h1> : <h1> Example data from API here </h1>}
    <footer> My footer is here </footer>
    </div>
    )
}
export default Conditional
```

0:14 -- I don't know how much longer I can stay up. Tomorrow morning there are some obligations outside of code that are going to require me to wake up early. 

0:15 -- With that being said... I don't care too much if my performance in those areas suffers. The most important thing in my life now is learning code. Let's continue with the next video!!!

0:18 -- The video I just finished watching is about the [logical && operator in the context of conditional rendering](https://scrimba.com/p/p7P5Hd/cDqbpcg). I'm going to watch the video again and take notes this time.

0:22 -- Let's quickly talk about how the logical && operator works under the hood in JavaScript. First, let's get some example code.

```javascript
if (string(i).length > 1 && arr.length < 10) {
    arr.push(string(i))
}
```

0:26 -- Looking at the above example, here's what JavaScript is doing under the hood. First, JavaScript is evaluating whether our expression that precedes the logical && operator is true or false. 

>If false, JavaScript will immediately return false.

If the first expression evaluates to true however, JavaScript will then evaluate the second expression (whatever code we've written on the right of the logical && operator) 

> Whatever the second expression evaluates to, that's what the logical && operator will return.

0:30 -- Because of the way the logical && operator behaves, it is often used in conjunction with conditional rendering.

0:32 -- Let me 'splain why this is the case my friend.

0:33 -- Let's say we have a condition. Based on that condition we either want to render something, or nothing. Here's how a noob might write said code:
```
return(
    <div>
{this.state.newMessages.length > 0 ? <h1> You're a popular pony, you have {this.state.newMessages.length} new messages  </h1> : null}
</div>
)
```
0:37 -- You probably figured out already that if there are any new messages the \<h1> and it's contents would be rendered. If there were no new messages, however, nothing would be rendered.

0:40 -- While the above code is technically valid, it's a bit verbose. Using the logical && operator we can shorten our code a bit. Check this out!

```
return (
<div>
this.state.newMessages.length > 0 && <h1> You're a popular pony, you have {this.state.newMessages.length} new messages  </h1>
</div>
)
```
The code block above performs exactly the same as using the ternary operator. 
>Different developers will structure their logic differently and it's likely you'll spend most of your time looking at code other developers have written. For that reason, it's important to always be aware of different ways of doing things even if you have your own individual preference.

0:49 -- It's getting late so I'm going to get to bed now. Good night!
___
17:41 -- Let's get to coding.

17:42 -- I've now moved on to the [conditional rendering practice video](https://scrimba.com/p/p7P5Hd/c893vh2) in Bob Ziroll's *Learn React for Free* course.

17:45 -- Here's the challenge:
> Given a stateless functional component:
> 1. Follow the steps necessary to add state to it,
> 2. Have state keep track of whether the user is logged in or not
>3. Add a button that logs the user in/out.
> *extra challenge* - make the button display "log in" if they're not logged in and "log out" if they are
>4. Display text that says "Logged in" if the user is logged in, or "Logged out" if they're not.

17:49 -- Let's get to work. The first thing I'm immediately wondering is if it will be necessary to create a conditional component... I think it will. I think I can create a conditional.js component and put my button in there.

17:52 -- Another thing I immediately thought about when presented this problem was whether we would have to convert the functional component to a class based component.

17:53 -- I was curious about this because I had not yet seen a functional component that implemented state. For that reason, I was not even sure if functional components were capable of implementing state. Well, my search reveals that they *aren't*.

Here's some great information I got from a [blog article](https://programmingwithmosh.com/react/react-functional-components/) on Mosh Hamedani's website:

> T"he key thing that makes this type of component (Note from Cam: Mosh is referring to functional components) different from a class component is the lack of state and lifecycle methods. This is why functional components are also commonly referred to as stateless components." -- Mosh

17:57 -- Basically, from my understanding, functional components are an interesting part of React because they actually have less functionality than class based components. When developers learn this, many ask, "*What then is the point of functional components*"?

17:59 -- It's very simple. Going over old code can be a time-consuming process. You have to understand why the old code was written the way it was.

Because functional components have less functionality (no pun intended), it's easier to understand what the original developer used said functional component for.

>Looking over class based components and trying to figure out what they are doing is more time consuming because class based components have a greater range of possible use cases. 

18:05 -- I just went even deeper down the rabbit hole. [According to David Jöch](https://medium.com/@Zwenza/functional-vs-class-components-in-react-231e3fbd7108), the React Hooks 16.8 update enabled developers to use the **useState** hook in functional components (and thus enables state usage in functional components).

In addition, you can now use the **useEffect** hook to implement lifecycle methods into your functional components.

18:11 -- I'm going to take a quick 5 minute break to stretch.

18:16 -- I'm finished stretching. Let's get back to the practice exercise now.

18:19 -- I've convered the functional based App component into a class based App component. Still a long way to go, but here's my start:

```
class App extends React.Component {
    constructor () {
        super ()
        this.state = {
           isLoggedIn: true 
        }
    }
    render() {
        return (
        <div>
            <Conditional />
        </div>
    )
    }
}

export default App
```

18:27 -- Still working. I've taken some steps that weren't technically necesssary just to get some extra practice in. You'll see in the code below for example that I simulated an API call with my componentDidMount and setTimeout methods:
```
class App extends React.Component {
    constructor () {
        super ()
        this.state = {
           isLoggedIn: true 
        }
    }
    
    componentDidMount() {
        setTimeout(() => this.setState({
            isLoggedIn: false
        }), 3000)
    }
    
    render() {
        console.log(this.state.isLoggedIn)
        return (

        <div>
            <Conditional isLoggedIn={this.state.isLoggedIn} />
        </div>
    )
    }
}
export default App
```

18:28 -- Also notice that I've got the good old console.log() method in there. That dude's been loyal to me since day 1 so I still make sure to let him participate in all my projects lol.

18:35 -- I'm on the home stretch. Based on whether the state of isLoggedIn is set to true or false my application will either render:
* You are currently logged in
* You are currently logged out

18:36 -- Here is what my code is looking like thus far...
**App.js**
```
import React from "react"
import Conditional from "./Conditional"

class App extends React.Component {
    constructor () {
        super ()
        this.state = {
           isLoggedIn: true 
        }
    }
    
    componentDidMount() {
        setTimeout(() => this.setState({
            isLoggedIn: false
        }), 3000)
    }
    
    render() {
        console.log(this.state.isLoggedIn)
        return (

        <div>
            <Conditional isLoggedIn={this.state.isLoggedIn} />
        </div>
    )
    }
}

export default App

```
And below... **Conditional.js**
```
import React from "react"

function Conditional (props) {
if (props.isLoggedIn) {
    return (<h1> You are currently logged in </h1>)
}
else {
    return (<h1> You are currently logged out </h1>)
}
}

export default Conditional
```

18:38 -- Am I finished yet? Of course not. There are still a few changes I need to make.
1. Render a clickable button that sets the state of isLoggedIn to the opposite of whatever its current value is.
1. Convert my *if else* statement in Conditional.js into a ternary operator to make it easier to read.
1. Remove the unnecessary setTimeout method from my application.

18:42 -- My eyes are feeling a bit dry right now. I'm going to take 5 minutes off to give them a rest and stretch my body again.

18:53 -- I'm back. Let's try to finish this app up.

18:58 -- Currently trying to figure out what's wrong with this code:

```
clickHandle () {
    this.setState(() => {
     const LoginStatus = !isLoggedIn
     isLoggedIn: LoginStatus
    })
}
```

I'm currently getting the following error:
> TypeError: Cannot read property 'setState' of undefined (/App.js:53)

19:05 -- **Epiphany!** I'm getting an error because I forgot to bind my clickHandle! 

Unrelated note: It turns out the naming convention isn't clickHandle, but handleClick. So, I've also gone and switched that out.

19:09 -- So, now I've got my click handler working. But... this is only passing a simple object to my setState() method. As a result, I can toggle from isLoggedIn true to false, but I cannot yet toggle from false to true.

```
import React from "react"
import Conditional from "./Conditional"


class App extends React.Component {
    constructor () {
        super ()
        this.state = {
           isLoggedIn: true 
        }
        this.handleClick = this.handleClick.bind(this)
    }

handleClick () {
    this.setState(
        {isLoggedIn: false})
}

    
    render() {
        console.log(this.state.isLoggedIn)
        return (

        <div>

            <Conditional isLoggedIn={this.state.isLoggedIn} />
                    <button onClick ={this.handleClick} > Log In/Out </button>
        </div>
    )
    }
}

export default App
```

19:11 -- I know I need to go about passing a function to my setState method... Let's see if I can successfully implement that.

19:15 -- Faultly logic... Give me 10 more minutes:
```
handleClick () {
    this.setState(() => {
       const update = !this.state.isLoggedIn
       isLoggedIn: update
    })
}
```

19:25 -- Still broken. Just broken in a more convulted way lol:

```
handleClick () {
    this.setState(() => {
        let updatedLog = undefined
        console.log(updatedLog)
    this.state.isLoggedIn ? updatedLog = false : updatedLog = true
 return updatedLog
 console.log(updatedLog)
    {isloggedIn: updatedLog} })
}
```

19:26 -- It doesn't matter if I flip the ternary arguments. For whatever reason, updatedLog always comes back as true.

19:34 -- I'm so confused beyond confused lol.

```
handleClick () {
    this.setState(() => {
       this.state = {
           updatedLog: !isLoggedIn
       }
       return this.state.updatedLog
    }, {isLoggedIn: this.state.updatedLog} 
    )
        
}
```
I can't find any solutions to toggle the state using my handleClick function. My eyes are *super* dry so I need to take a break now. Hopefully I can find a solution later tonight.

___
**Total time spent coding today**: N/A
___
**Total time spent coding thus far in May 2019**: N/A
___
**Total lifetime hours of coding**: N/A