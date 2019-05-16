# Wednesday May 15th, 2019 Daily Coding Journal

8:46 -- I'm going to get this journal entry setup and then do some React work.

8:54 -- I looked back at the journal entry from yesterday, and it looks great on GitHub! I'm really happy how things turned out. Now... let's get back to React.

9:08 -- For the first time, I've finally been able to come to the solution on my own! Here's my code:
```javascript
handleChange(id) {
        this.setState( prevState => {
        const updatedTodos = prevState.todos.map(todo =>{
            if (todo.id === id) {
                todo.completed = !todo.completed
            }
            return todo
        }) //map closing bracket and parentheses
        return {todos: updatedTodos}
        }
        )
    }
```
I'm a little short on time now so I can't explain why I did everything I did above. In 1.5 hours, however, I'll come back to this journal entry, solve the problem again, and talk about my feelings on the above problem.
___
10:43 -- Did I remember to mention how much I love these horizontal rules using markdown? Seriously, I love how clean they make everything look. I also love that on GitHub I can view things both properly formatted or alternatively can view the raw markdown. Anyway, I'm going to solve the React checking and unchecking activity again. Then, I'll move to the next exercise. Hopefully they give me a breather and take a break on ramping up the difficulty any further for a video or two lol.

11:00 -- Well, I've done it. I've solved the problem again, and I've got to say, it's still not easy. But... I feel like things are finally starting to click. I made a few errors in solving the problem such as forgetting to set my new state using brackets { }, but I was able to figure everything out after a big of debugging.

Here are my different files and the the code contained within each file...

**App.js**:
```javascript
import React from "react"
import TodoItem from "./TodoItem"
import todosData from "./todosData"

class App extends React.Component {
    constructor() {
        super()
        this.state = {
            todos: todosData
        }
        this.handleChange = this.handleChange.bind(this)
    }
    
    handleChange(id) {
     this.setState(prevState => {
         const changedTodos = prevState.todos.map(itemTodo => {
             if (itemTodo.id === id) {
                 itemTodo.completed = !itemTodo.completed
             }
             return itemTodo
         }) // closing bracket and parenthesis for .map() method
         return {todos: changedTodos}
     }) // closing bracket and parenthesis for .setState() method
    }
    
    render() {
        const todoItems = this.state.todos.map(item => <TodoItem key={item.id} item={item} handle={this.handleChange} />)
        
        return (
            <div className="todo-list">
                {todoItems}
            </div>
        )    
    }
}

export default App
```
**TodoItem.js**:
```javascript
import React from "react"

function TodoItem(props) {
    return (
        <div className="todo-item">
            <input 
                type="checkbox" 
                checked={props.item.completed} 
                onChange={() => props.handle(props.item.id) }
            />
            <p>{props.item.text}</p>
        </div>
    )
}

export default TodoItem
```
I won't include other parts of the project because they were already mostly setup by the instructor versus something I had to actually code myself. In any case, I'm excited to finally move on to the next exercise!

11:09 -- The next video is about Lifecycle methods in React. The following notes were inspired by [this video](https://scrimba.com/p/p7P5Hd/cewQ2Sq).

11:10 -- Every React component will undergo a series of events when it's being rendered and updated.

11:11 -- The React team has recently deprecated 3 of the original lifecycle methods.

11:14 -- The render method can be called many times. Anytime React determines something has changed such as states or props, basically anything that affects how the component is supposed to display, React may run the render method again.

11:15 -- I'm going to go eat brunch now before the restaurant closes. I'll finish taking the rest of the notes for this video later.
___




___
___
___
___
___
___
___
___
___
___
___
___
___
___
___
___
___
___
___
___
___
___
___
___
___
___
___
___

Total time spent coding today: N/A
___
Total time spent coding thus far in May 2019: N/A
___
Total lifetime hours of coding: N/A