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

**Total time spent coding today**: N/A
___
**Total time spent coding thus far in May 2019**: N/A
___
**Total lifetime hours of coding**: N/A