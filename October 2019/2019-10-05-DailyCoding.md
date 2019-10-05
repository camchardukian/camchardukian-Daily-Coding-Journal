# Saturday October 5th, 2019 Daily Coding Journal


18:41 — It’s been a long week. This week I’ve already spent 40.75 hours working as an employed developer, 6.75 hours teaching English, 0.5 hours on my blog/youtube, and another 7 hours learning programming on my own time. 

I’ve also spent another 8.75 hours practicing Vietnamese with the girl I’m dating… but that’s just of ancillary importance.

The point is that it’s been a long week already, but I’m still showing up on Saturday night to put in a little extra work to improve my skills.

In this session I’m going to study props in React to better understand them at a conceptual level. They are one of the fundamentals in React, but sometimes I make mistakes when using them so they are certainly worth spending a little time sharpening my skills on.

18:47 — I’m taking some notes from [this video on props](https://www.youtube.com/watch?v=m7OWXtbiXX8):

— We use parentheses when we split our JSX into multiple lines.

— If we know exactly what properties are going to be passed as props, we can pass them as attributes.

When we are not sure exactly what we’re going to pass, however, or if we need to pass dynamic HTML content, we can pass said content in between the content tags of our child component and pass these unknown props using *props.children*.

— *this.props* is a reserved (keyword?)inside of class components that we can use to access our props.

— Props are immutable. This means that our React components need to act like pure functions (just like how reducers in Redux need to be pure functions).

19:01 — I’m watching the first half of [this video](https://www.youtube.com/watch?v=4ORZ1GmjaMc) to better understand the differences between props and state:

— Props get passed to a component while state is managed within the component.

— Props are immutable. State on the other hand can be changed.

— To access props in functional components we use *props* and use *this.props* in class components. To use state in functional components we can use the useState Hook, while in class components we’d use this.state.

19:04 — Now I’m going to watch exactly the type of video that my team leader said I should watch. This [next video](https://www.youtube.com/watch?v=QpfyjwhY9kg) is about how we can pass methods as props.

— Children components can also communicate with their parents via the use of props.

— It is possible for a child component to call a parent component’s method. 

— We do this by passing the parent component’s method as a prop to the child component, (and we could then use some type of event handler to then utilize the prop from the parent component).

— I’ll try to put some type of code example together for the above explanation…

19:51 — When we have class components, we should declare state, and if necessary, bind our methods inside of our constructor.

19:54 — So, using the help of a tutorial, I just build a *very* *very* basic app that has a child component call a parent component’s method via the use of props and an onClick event handler.

I’ll try to rebuild this application from scratch again tomorrow for practice. For now though, it’s getting late and I’d like to get dinner hang out with my girl for a couple hours before waking up early to teach English tomorrow.

It's not unearned after a solid 56+ hours of work this week :))

___
**Total time spent working as an employed developer today**: N/A

**Total time spent practicing code outside of work today**: 1 hour 20 minutes

**Total time spent practicing code outside of work thus far in October 2019**: 5 hours 28 minutes

**Total lifetime hours practicing code outside of a job**: 739 hours 7 minutes

**Total lifetime hours working as an employed developer**: 252 hours 49 minutes











































