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
**Total time spent coding today**: N/A
___
**Total time spent coding thus far in May 2019**: N/A
___
**Total lifetime hours of coding**: N/A