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

14:45 -- I've only got about 15 minutes but let's see if we can do some damage here.

14:48 -- Another lifecycle method we should know is the componentDidMount() method. The syntax for this method is as follows
```
componentDidMount() {

} 
```
14:50 -- The **componentDidMount** () method is a method that is run the very first time our component shows up. What's a practical use case for this method? One common occurence is using componentDidMount for API calls. In a hypothetical food list for example, we only need to make a request to the server one time for information on the nutritional values of foods because their caloric density or vitamin content aren't going to change from minute to minute.

14:55 -- Another common lifecycle method is called **componentWillReceiveProps**(). The syntax for this method as you may expect is:
```
componentWillReceiveProps() {        

}
```
This method also often receives a parameter of *nextProps*. In other words, you may often see it written as:
```
componentWillReceiveProps(nextProps) {

    }
```
15:01 -- Gotta go. I'll explain componentWillReceiveProps() in more detail later.
___
16:49 -- I'm back... And let's get back to the componentWillReceiveProps() method.

16:52 -- It turns out that componentWillReceiveProps was actually deprecated starting in React 16.3. While it may be useful to be aware of this lifecycle method when using legacy code, we will no longer use it when building new React applications.

16:54 -- The next lifecycle method we're going to look at is called **shouldComponentUpdate**()

16:59 -- Whenever React has any concern whatsoever that your component may need to rerender, React will always choose to rerender our component just in case. 

Unfortunately, this decision is made without any concern of the specifics of our application. Sometimes React will rerender a component even if nothing about that component has changed.

Unfortunately, this can quickly become resource intensive if we allow this to happen to dozens, hundreds, or even thousands of components.

This makes a lot of sense. Connecting this to [what I read earlier today](https://reactjs.org/docs/faq-versioning.html) about Facebook's codebase having over 50,000 components, I can't imagine how slow Facebook would be if React was constantly randomly rendering all of those components unnecessarily.

17:08 -- Basically, the main idea of that huge chunk of text above is that using shouldComponentUpdate we can optimize the performance of our application.

17:09 -- So the next question becomes, *How do we use this lifecycle method to help React determine whether it should update a component or not?*

17:13 -- Here's what we can do -- use a couple powerful parameters along with some logic. Let's talk about the parameters first. The shouldComponentUpdate() method takes two parameters commonly called by convention: *nextProps* and *nextState*.

17:19 -- I'm guessing, however, that just reading all of this doesn't make things very clear though. Here's a quick code block to visualize what we're working with.
```
shouldComponentUpdate(nextProps, nextState) {
        // insert logic here
    }
```

17:21 -- Let me explain what I mean above by insert logic. Inside of our shouldComponentUpdate() method we're going to put some kind of logic that'll either return true or false. If said logic returns true, we *will* update that component. If the logic returns false, however, our component will not update. Here's another code block to help you visualize things:

```
    shouldComponentUpdate(nextProps, nextState) {
        // return true if update desired
        // return false if not
    }
```

17:24 -- Now, let's review the pros and cons of how conservative we are in updating or not updating components. If we always update components, we're less likely to have bugs, but our application will run slower. Conversely, updates that occur too infrequently can lead to hard debug errors. Like most things in life, finding the proper balance is very key.

17:26 -- That's all I've got for now. In the next pomodoro session we'll start to talk about the componentWillUnmount() lifecycle method.
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