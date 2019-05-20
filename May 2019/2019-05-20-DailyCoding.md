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

When I come back I'll try to apply what I've learned about using CSS in React to style elements based on what their state is currently set to.
___

10:02 -- I'm back. I feel so full now. I just ate a tray of jackfruit along with a takeaway box of Bun Thit Nuong. Hopefully I don't doze off during this programming session lol.

10:05 -- This line of code immediately jumps out to me as a starting point for where I should begin styling, or at least where to begin my investigation on how to style these elements.

```
<p>{props.item.text}</p>
```

10:07 -- I also suspect this line of code I've just written relates to the solution:
```
{console.log(props.item.completed)}
```

10:27 -- I've completed the challenge. This one required a little bit of thinking, but was not excessively difficult. Here's my code inside of TodoItem.js:
```
import React from "react"

function TodoItem(props) {
    const styles = {
        fontSize: 24
    }
    
    props.item.completed ? styles.color = '#C0C0C0' : styles.color = "#000"
    props.item.completed ? styles.fontWeight = 'bold' : styles.fontWeight = "lighter"
    return (
        
        <div className="todo-item">
            <input 
                type="checkbox" 
                checked={props.item.completed} 
                onChange={() => props.handleChange(props.item.id)}
            />
            
            <p style = {styles}>{props.item.text}</p>
            
        </div>
    )
}

export default TodoItem
```

10:30 -- My code above changes completed todoItems to be a gray color, while it changes incomplete items to be black and in bold text.

10:31 -- Now I'm going to view the instructor's implementation and see if he approached this problem any differently. Maybe I'll be able to pick up a trick or two.

10:33 -- Well, the instructor definitely conformed to the DRY (don't repeat yourself) programming principle a lot more effectively than I. Instead of using multiple ternary operators, he chose to only style the completed todo items.

Given his alternative method of styling, he simply assigned all of his properties he wanted to completed todo items, and used a single ternary operator to choose whether his class would be applied to the individual todoItem.

While my method allowed for the styling of both completed, and incompleted todoitems, I definitely learned from his approach as well.

10:39 -- My body is feeling a little tight. I'm going to take a quick 5 minute break, and then come back and take notes on the next video in the course [*Fetching data from an API*](https://scrimba.com/p/p7P5Hd/c79Jask).

10:47 -- I'm back. Let's get to those notes. Actually, I think I'll watch the video first all the way through without pausing for a quick overview. Then I'll watch it again, take notes, and try to get a deeper understanding of the material.

10:56 -- I think I'm going to have to bolt. I'm at the convenient store and I've been waiting to go to the bathroom for like 30 minutes now, but somebody's been in there forever. I can't focus anymore lol.

10:57 -- I'll quick upload this journal to GitHub, walk home and eat another Bun Thit Nuong on the way there, and then maybe take a nap when I get home.
___

16:57 -- I slept for nearly two hours, plus had lunch and other professional obligations I had to attend to. Regardless, now I'm ready to finally take notes on APIs!

17:00 -- The first minute or two of the video were just reviewing the **componentDidMount( )** lifecycle method.

17:01 -- *Fetch* is a relatively new built-in JavaScript tool that offers a promise-based way to perform HTTP requests in order for us to get data.

17:05 -- This tutorial uses the [Star Wars API](https://swapi.co/) as it's one of the more simple APIs out there.

17:08 -- [The tutorial](https://scrimba.com/p/p7P5Hd/c79Jask) recommends getting a solid grasp of promises in order to better understand how fetching data from an API works.

17:10 -- Here are a few notes from [this article](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261) on promises (Some bullets are taken word for word from the article. Those I've indicated with double quotes. Anything not in double quotes is my paraphrased interpretation of the article.)

* >"A promise is an object that may produce a single value some time in the future: either a resolved value, or a reason that it’s not resolved (e.g., a network error occurred)."
* Any promise will be set to one of three possible states that include:
    * Fulfilled
    * Rejected
    * Pending
* While promises have been around in different programming languages for decades, they have recently increased in popularity in JavaScript in large part to the *Promise* global introduced in ES6.
* Promises that have already been settled are immutable (or in simpler terms.... unchangeable).
* Promises can be chained.
* The author of the cited article recommends ending all promise chains with the .catch() method (supposedly because doing so helps prevent errors from going undetected or being "swallowed").
* >"Only the function that creates the promise should be able to resolve, reject, or cancel the promise."
* There may be times when you are programming and you need to insert a function somewhere to prevent errors from occuring, but you don't necessarily need said function to do anything. In that situation, it's recommended you follow the naming convention and call your function noop() which is short for no-op (no-operation I presume).

17:26 -- I've finished skimming the above article. To be honest, I still feel pretty sketchy on promises. I think I'm going to have to watch several videos and maybe do some exercises to get the hang of them. I'm going to walk home and then I'll watch some videos on promises in an hour or two.

___
19:46 -- I paid rent, went for a couple walks, took a shower, ate some strawberries, and now it's time to get back to learning about promises.

19:48 -- I'm going to build on my knowledge of promises by watching and taking notes on [this video](https://www.youtube.com/watch?v=2d7s3spWAzo&) from the FunFunFunction Youtube channel. I find in general that this developer does an excellent job of introducing new concepts to developers.

19:52 -- promise has a method called *.then()*.

19:53 -- MPJ (the name of the developer that created the video) compares promises in JavaScript to promises in the real-world. Let's illustrate this...
>If you go to the bank, they may promise to lend you a certain amount of money. When you are looking to buy a house, you can then tell your real estate agent how much money the bank was willing to lend to you and make a contract based on the bank's promise -- despite the fact that you haven't actually yet received any of that money.

Or, to quote MPJ directly, 
>"A promise is something you can pass around and write code around it even though you don't have the value you just yet." 

19:59 -- MPJ just went on a rant about the *node.js Christmas tree of doom*. Or basically, the idea that having an excessive number of callback functions does not comply with the DRY programming principle.

20:04 -- The promise constructor takes a single callback function as its argument. This callback function then takes by convention two arguments; *resolve* and *reject*.

As if this wasn't convulted enough, it turns out resolve and reject are also functions in their own right! O_O

20:12 -- MPJ says that promises are more helpful to us than callbacks due to the fact that promises compose.

20:15 -- The .catch() method along with the argument of error and a callback function can help us "catch" (I don't fully understand yet, so I won't try to clarify catch in my own words) any errors that occur during the promise process:
```
.catch((error) => {
 // I think you put what will happen if there is an error here.
})
```

20:19 -- Here are some closing notes from MPJ:
* Promises are closely related to callbacks.
* Both can be used to deal with asynchronous code when we don't know when something is going to happen.
* Promises are more powerful than callbacks because they compose.

20:24 -- I must admit that I feel as though I still don't really "get" promises. I need to take a break to let the previous video incubate in my head a bit.

20:25 -- When I come back I'll watch [Coding Train's video on promises](https://www.youtube.com/watch?v=QO4NXhWo_NM). I'm sure I'll be at least somewhat more comfortable with promises after watching and taking notes on his 2-part 35 minutes series on JavaScript promises.

20:26 -- Catch you later!
___
**Total time spent coding today**: N/A
___
**Total time spent coding thus far in May 2019**: N/A
___
**Total lifetime hours of coding**: N/A