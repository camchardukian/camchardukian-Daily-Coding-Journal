# Sunday November 24th, 2019 Daily Coding Journal

16:28 — After a one day break yesterday, it’s time to get back to the coding grind.

16:45 — We can do prop validation to validate a whether a prop is one of the following types using this syntax:
```
yourPropName: PropTypes.oneOfType([
PropTypes.string, PropTypes.number
)]
```

16:50 — Now that I’ve just finished the **Introduction** section of the course, it’s now time to move on to section 2 — **Reusability**

16:52 — Here are my notes for video #1 in the Reusability section of Scrimba’s “The React Bootcamp”.

## Code Reuse in React:

— Reusing code allows us to more easily maintain our application and reduces the likelihood of human error.

— In the [React documentation](https://reactjs.org/docs/composition-vs-inheritance.html#so-what-about-inheritance), the Facebook team recommends using composition over inheritance.

— Some of the coding patterns that exist to help us make our code more reusable in React are…
1. Components (especially those with props)
1. Children
1. Higher-order Components
1. Render props

___

17:02 — My neck is starting to feel a little stiff as I’m hunched over my laptop in the convenience store right now. I’m going to take a break, and try to come back to take more notes later tonight.

17:53 — I’m back. I’m getting a message at 19:00, so let’s try to get in ~45 minutes or so before calling it a day and pushing this journal entry to GitHub.

17:54 — Let’s take some more notes.

 ## React Children:

— Any component we create can be used as both a self-enclosing and non-self enclosing element.

— If we create a component, make it non-self enclosing, and then give it children; we can access those children from the parent component using props.children.

— While they have mostly the same utility, in general, using children is beneficial for giving the developer maximum flexibility. Using props is beneficial for maximum certainty that the developer will use our component correctly.
___

18:22 — I just finished one of the course’s exercises on React children. After that exercise, I feel I have a much better understanding of the relationship between parent and children in React.

18:23 — Let’s take some more notes!

## HOCs Part 1:

— Higher order components basically come from the idea of higher order functions.

— The basic idea of a higher order component is to have a component that takes another component as an argument and then the original component gives the component passed as an argument some additional functionality.

— While doing so is not required, a popular convention amongst React developers is to use the word “*with*” at the beginning of one’s higher order component.
___
## HOCs Part 2:
— If we give a prop to our higher order component, that prop will be passed and available for use in the component that is returned and wrapped by the HOC.
___
18:45 — I just finished one of the practice exercises on higher order components. Now I’m going to get ready for my first massage in 2.5 months. It’s been well earned after hundreds and hundreds of hours on the coding grind the last few months.

I’m not sure if I’ll get another study session in tonight. If so, I’ll obviously take more notes. If not, I’ll just quickly update this journal entry later, and push everything to GitHub.
___
21:20 — I just finished my massage, and it’s nearly time for bed. Let’s see, however, if we can fit in another 15 minutes or so of coding before bed.

21:34 — It’s been a solid day. I’m going to get a little something to eat, and then get ready for bed.
___
**Total time spent working as an employed developer today**: N/A

**Total time spent practicing code outside of work today**: 1 hour 56 minutes

**Total time spent practicing code outside of work thus far in November 2019**: 20 hours 12 minutes

**Total lifetime hours practicing code outside of a job**: 784 hours 35 minutes

**Total lifetime hours working as an employed developer**: 537 hours 16 minutes