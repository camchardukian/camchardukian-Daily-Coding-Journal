# Monday September 15th, 2019 Daily Coding Journal

11:29 — I’m finally starting to feel somewhat better today, but not to the point where I feel like I could legitimately focus for a full 8+ hour workday. Today I’m going to try to finish Dan Abramov’s Redux course. Let’s get started!

Here are my notes for video 14 of the course: [Redux: Reducer Composition with Objects](https://egghead.io/lessons/react-redux-reducer-composition-with-objects):

— One reducer can be called by another reducer.

— Redux development is scalable largely because it prevents a significant portion of merge conflicts by allowing different members of a team to work on different reducers that handle the same actions.

11:44 — Here are my notes for video 15 of the course: [Redux: Reducer Composition with combineReducers()](https://egghead.io/lessons/react-redux-reducer-composition-with-combinereducers):

— The combineReducers() function does pretty much what you’d expect it to do — It takes several reducers that we pass into it and generate a “big reducer” (it looks like in technical terms they’d call this a top level reducer) from all of them.

— The only argument we pass to the combineReducers() function is an object. This object specifies which pieces of state are being managed by which reducers. In this object, the keys are the pieces of state that the object is going to manage, while the values are the reducers that will manage each piece of state.

— ES6 offers something called object literal shorthand notation. This basically means that if the name of our keys is the same as the name of our values, we can omit writing the values in our code. For example:

```
combineReducers({
todos: todos,
visibilityFilter: visibilityFilter
})
```
is exactly the same as:
```
combineReducers({
todos,
visibilityFilter
});
```
— Because of the object literal shorthand notation I just discussed above, many developers by convention will name their reducers after the piece of state that they manage.

— While I am not sure yet why a developer would want to, I do know from reading a comment by Dan Abramov that it’s possible to use combineReducers() multiple times in our application.

11:58 — Here are my notes for video 16 of the course: [Redux: Implementing combineReducers from Scratch](https://egghead.io/lessons/react-redux-implementing-combinereducers-from-scratch):

— In this video, Dan basically showed us what the combineReducers() function is doing under the hood by creating an equivalent function from scratch.

12:07 — Here are my notes for video 17 of the course: [Redux: React Todo List Example (Adding a Todo)](https://egghead.io/lessons/react-redux-react-todo-list-example-adding-a-todo):

— It is common for React components to dispatch actions in Redux applications. Dan also says,
>My ToDo app component assumes that it’s going to receive ToDos as a prop, and it maps over the ToDo list to display a list of them using the ID as a key.

— Looking at the above quote, I think I’ve finally realized the importance of mapStateToProps(). By using mapStateToProps() we can give our component access to the specific piece of state it needs access to in order to update the view being rendered to our users! #Epiphany

12:25 — Here are some notes I just took from a [related blog post on another website](https://learn.co/lessons/map-state-to-props-readme):
— The React Redux library has a component called *Provider*. We can use this component (Provider) and wrap it around our *App* component. Doing so does two things.

Our Redux application will be alerted when there is a change in state, and our React application will then be re-rendered. In other words, Provider helps us make sure that our entire React application has the potential to access data from the Redux store.

— The *connect()* method allows us to specify which piece of data/state we are listening to, and which component we want to provide that data/state.

12:30 — This has been a very productive hour. I’m feeling a lot more confident on mapStateToProps(), and even more comfortable than I was before about the combineReducers() function. I’m going to take a break, and head to video 18 in the course soon.
___

14:17 — I’m back. My break was a little bit longer than I anticipated, but I’m ready to learn some more. Let’s get another hour or so of learning in before lunch.

Here are my notes for video 18 in the course: [Redux: React Todo List Example (Toggling a Todo)](https://egghead.io/lessons/react-redux-react-todo-list-example-toggling-a-todo):

— This video was basically a review of Redux flow. One interested bit I did pick up, however, is that we need to give our list items an *id* property in order for us to clearly indicate which list item we are intending to modify the state of in the case of something like a todo application or statistics table.

14:32 — Here are my notes for video 19 in the course: [Redux: React Todo List Example (Filtering Todos)](https://egghead.io/lessons/react-redux-react-todo-list-example-filtering-todos):

— I saw a simple real-world use case of destructuring, and how it can lead to us writing shorter, cleaner code.

— This video also helped me strengthen my understanding of props and their role in both React and Redux.

15:05 — Just took a 5-10 minute break because I was feeling tired and needed to renew my focus. Let’s go for another 20 minutes or so now.

Here are my notes for video 20 in this course [Redux: Extracting Presentational Components (Todo, TodoList)](https://egghead.io/lessons/react-redux-extracting-presentational-components-todo-todolist):

— This lesson basically introduced the idea that in any non-trivial sized application, we’re going to want to have multiple components. This “multi-component” approach allows us or our team of developers to work more effectively by having many components that can be used, tested, and changed.

15:16 — Here are some notes I took from a [related article](https://www.fullstackreact.com/p/using-presentational-and-container-components-with-redux/) I read on another website:

— In React, a presentational component is a component that just refers HTML.

— In an application that utilizes Redux, a presentational component does not interact with the Redux store.

— Presentational components accept props from container components.

— Container components specify which data a presentational component should render.


15:21 — Here are my notes for video 21 in this course[Redux: Extracting Presentational Components(AddTodo, Footer, FilterLink)](https://egghead.io/lessons/react-redux-extracting-presentational-components-addtodo-footer-filterlink):

— It’s recommended to seperate presentational components because doing so separates our rendering from Redux which gives us flexibility
to more easily switch technologies later if necessary.

15:32 — Whoa. I’m pretty exhausted now. I’m going to eat lunch and get some rest…

___
21:43 -- After lunch, I ended up taking an accidental nap of nearly two hours. I was just waiting for my girl to finish eating, and I just passed out.

I guess my health hasn't fully returned yet. In any case, despite being sick, I got a solid 5+ hours of Redux instruction in this weekend.

While I'm not yet fully sold on my abilities to work with Redux, I think that this week I'll at least "be able to get stuck" instead of feeling so hopeless that I basically can't start.

I think that I'm getting to the point now with my Redux knowledge where I can at least begin to ask semi-intelligent questions about why something isn't working.

Tomorrow I'll head back to working as a developer. For that reason, tonight I'm going to try to get some extra sleep.

While I didn't finish the Dan Abramov Redux course this weekend as I originally intended. I did get through the majority of it, and I feel much more confident now. I'll try to finish the rest of it the next several days.
___
**Total time spent working as an employed developer today**: N/A

**Total time spent practicing code outside of work today**: 2 hour 23 minutes

**Total time spent practicing code outside of work thus far in September 2019**: 22 hours 38 minutes

**Total lifetime hours practicing code outside of a job**: 723 hours 13 minutes

**Total lifetime hours working as an employed developer**: 137 hours 36 minutes