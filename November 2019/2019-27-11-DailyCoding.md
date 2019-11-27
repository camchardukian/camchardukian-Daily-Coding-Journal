# Wednesday November 27th, 2019 Daily Coding Journal

21:35 -- Today was a pretty light day of work at the office. I refactored some old code, and then suggested some new tasks I could start working on, but my team lead just wanted me to wait for the back-end developer to finish some APIs. 

Thus, I spent most of the afternoon just reading documentation, learning more about React and improving my CSS Flexbox skills.

21:37 -- Here's what my day at the office looked like:
```

7:50 - 8:00
Connected keyboard.

Connected mouse.

8:00 - 11:45
Scrum meeting.

Caught up on Chatwork/email

Refactored company profile page code

11:45 - 12:45
Lunch/nap

12:45 - 5:00

Researched and took notes to deepen my knowledge of ReactJS and CSS Flexbox while waiting for additional tasks to be assigned.

Resources:
Render Props tutorial: https://www.youtube.com/watch?v=EZil2OTyB4w

React Redux Vs Context API: https://www.academind.com/learn/react/redux-vs-context-api/

300+ ReactJS Interview Questions (300+ things ReactJS developers should know): https://github.com/sudheerj/reactjs-interview-questions

Difference between space-around and space-between in Flexbox: https://medium.com/@sterlingcobb/flexbox-difference-between-space-between-and-space-around-d2751c446f61

Website with games for learning CSS Flexbox, CSS Grid, JavaScript Scope etc. : https://codepip.com/games/

Flexbox Froggy game for learning CSS flexbox: https://flexboxfroggy.com/

Notes:
One way to solve circular dependencies is to use absolute paths (though I’m not sure how architecturally sound this method is, it at least works temporarily in avoiding ESLint errors).

Render props are like ordinary props, but instead of passing a simple value like a string or object to the component, they actually pass a function.

By convention, we use the word *render* when passing a render prop.

Basically, like this video said (https://www.youtube.com/watch?v=EZil2OTyB4w), render props are a technique for sharing code between React components using a prop whose value is a function.

React’s Context API allows us to pass data through our component tree without having to manually pass props through every level of the component tree.

For the time being, it seems that while React’s Context API is suitable for applications with low frequency state updates, it does not yet offer optimal performance as a state management system that governs an application with a high frequency of state changes.

The problem with updating state directly is that doing so won’t re-render our component.

Lifting state up in React refers to the idea that if two child components in React are sharing the same data from a parent, that it makes sense to move the state to the parent instead of maintaining local state in both children.

Reconciliation refers to the process of React updating a component’s props or some state change occurring, and then comparing the newly returned element to the previously rendered element to decide if a DOM update is necessary.

There is a small performance benefit to replacing div tags with Rect fragments because Fragments use less memory due to the fact that they do not create another DOM node.

Hooks are generally seen as a simpler replacement to render props and higher order components because they reduce nesting in our component tree.

A switching component is a component that renders one of many components.

The usage of isMounted() with setState() is often an anti-pattern because while it may help us to avoid warnings, it also defeats the purpose of the warnings. Instead, we should instead try to resolve the underlying problem, which in many cases would be a callback function that is waiting for some data to arrive, and that isn’t properly canceled prior to our component unmounting.

We can’t iterate using for loops inside of JSX tags (if we need to loop we should just use Array.map()).

We can use window.addEventListener(‘resize’, this.ourFunctionName) inside of our componentDidMount lifecycle method to re-render the view or perform some other action whenever the user resizes their window.

The difference between setState() and replaceState() is that setState() merges the current state with the previous state while replaceState() throws out the previous state and the current state becomes whatever information you just provided.

React’s philosophy regarding props is that props should be immutable and top-down. This means that a child cannot modify props it receives from a parent.

The developers of Redux almost always recommend we access the redux store via the connect() higher order component rather than trying to access the store directly.

Developers generally see redux-thunk as having less of a learning curve while redux-saga is seen as being more powerful.

Render hijacking is basically a concept that refers to the idea of being able to control what a component will output via another component (think how a higher order component would change how another component behaves).

Service workers help to cache files and other assets to produce a better experience for users when they are offline or have a slow network connection.

There are two lifecycle methods that are directly related to error handling in React, *static getDerivedStateFromError()* and *componentDidCatch()*.

We can use ReactDOM.unmountComponentAtNode() to remove a mounted React component from the DOM, and clean up its event handlers and state.

At this time, keys are the only attributes that can be passed to React Fragments. There is talk, however, about providing support for event handlers to Fragments in the future.

Higher order components should not be applied in the render method of a component because they may cause excess re-rendering.

We can use the Lodash _.throttle function to only allow a function to be called AT MOST every “x” milliseconds.

We can return null (based on some condition) to only allow a component to render under certain conditions.

While keys in React should be unique amongst their siblings, our keys do not need to be unique within the global scope.

Refs are not passed via higher order components because refs are not props. In order to pass refs via higher order components, we need to use the React.forwardRef API.

Windowing is a technique in which we render only a small subset of a long list of data. This improves performance by reducing render speed and decreasing the number of DOM nodes our application creates.

We can use the order property in flex box to change the ordered position of a single element in CSS Flexbox if reversing our list of items isn’t enough.

CSS Flexbox also has a flex-wrap property which can be used to influence whether we want to try to squeeze all of our items on to one line or allow them to *wrap* or *wrap-reverse* to additional lines.

In CSS Flexbox, we can use flex-flow as a shorthand for flex-direction and flex-wrap. Flex-flow takes the same values as flex-direction and flex-wrap with a space between them.

In CSS Flexbox, we can use the *align-content* property to determine the spacing between multiple lines of items.
```

21:40 -- As you can see, I really took advantage of my team's "down-time" to better myself. I saw this afternoon as a great opportunity to learn more and become slightly more knowledgable than I was yesterday.

I also spent about 30 or 35 minutes after work watching some videos and doing exercises regarding render props.

But, it's getting late now so let's eat dinner, and get ready for bed.

In any case, it's geti
___
**Total time spent working as an employed developer today**: 8 hours 8 minute

**Total time spent practicing code outside of work today**: 36 minutes

**Total time spent practicing code outside of work thus far in November 2019**: 22 hours 47minutes

**Total lifetime hours practicing code outside of a job**: 787 hours 10 minutes

**Total lifetime hours working as an employed developer**: 561 hours 26 minutes