# Sunday September 15th, 2019 Daily Coding Journal

12:22 — I just finished lunch. Getting a bit of a late start today, but let’s not delay things any further! Today I’m continuing with [Dan Abrahamov’s course on Redux basics](https://learnreduxwithdanabramov.com/).

12:24 — Here are my notes for video 8 in the course: [Redux: React Counter Example](https://egghead.io/lessons/react-redux-react-counter-example):

— The ReactDOM.render() function in React will run whenever our Redux store’s state is updated.

— Dan Abraham recommends using functional components over classes whenever possible. He recommends using classes only when you need *this.state* or lifecycle hooks (methods) like *componentDidMount*.

12:38 — Here are my notes for video 9: [Redux: Avoiding Array Mutations with concat(), slice, and …spread](https://egghead.io/lessons/react-redux-avoiding-array-mutations-with-concat-slice-and-spread):

— We want our Redux code to be free of mutations. In other words, if we’re working with an array we don’t want to modify the original array. Basically, the gist of the lesson is that instead of modifying the original array we want to create a new array that contains the values we want it to contain.

12:46 — Here are my notes for video 10: [Redux: Avoiding Object Mutations with Object.assign() and …spread](https://egghead.io/lessons/react-redux-avoiding-object-mutations-with-object-assign-and-spread):

—A polyfill is code that helps browsers take advantage of features that they would not otherwise be able to support.

— Similar to not wanting to mutate our arrays, we also don’t want to mutate our objects in JavaScript. We can avoid mutating objects by using the Object.assign method or spread operator.

— Objects in JavaScript have a method called *assign* which can be used to copy or merge objects.

— If we want to copy an object, the first parameter passed into Object.assign would be an empty object (set of curly braces), and then the source object that we want to copy.

— If we want to merge two objects using the Object.assign method, we could pass one set of properties as our first argument, and another object as our second argument, and assign everything to a variable.

That variable would then contain all of the properties and values from both objects. One important thing to note is that the second argument effectively overwrites the first arguments properties/values if there are any conflicts.

This is essentially the same as if we assigned a value to a variable and then later assigned another value to that same variable.

13:46 — Here are my notes for video 11: [Redux: Writing a TodoList Reducer (Adding a Todo)](https://egghead.io/lessons/react-redux-writing-a-todo-list-reducer-adding-a-todo):

— Ehhh… this video was mostly a review of not mutating arrays/objects, and basic Redux flow of how a reducer will do one thing if its switch case matches the dispatched action’s type, and if an unknown action type is passed the reducer should simply return the original state of the object.

14:00 — Here are my notes for video 12: [Redux: Writing a Todo List Reducer (Toggling a Todo)](https://egghead.io/lessons/react-redux-writing-a-todo-list-reducer-toggling-a-todo):

— We’re reminded that reducers must be written as pure functions.

14:05 — I’ve put in about an hour and 10 minutes of studying thus far today. I’m feeling pretty tired now, however, and my battery is at 11% with no way of charging it (I’m working from an upscale mall’s food court).

For that reason, I’m going to walk around a bit, try to relax with my girl, and gain some energy for another coding session or two later today. See you then..

___

23:39 — I haven’t gotten around to doing nearly as much coding as I’d hoped today. My energy hasn’t been what I’d hoped it would be.

Being unable to get a taxi/car to drive us back, and having to walk in the rain probably didn't help either.

I’m going to try to do one more video in this course tonight before committing this journal entry to GitHub and heading to bed.

Hopefully, tomorrow I'll finally start feeling like myself again. Today I've still had some pretty moderate health issues that made going into work pretty far out of the question.

23:42 — Here are my notes for video 13: [Redux: Reducer Composition with Arrays](https://egghead.io/lessons/react-redux-reducer-composition-with-arrays):

—Reducers are normal JavaScript functions. This means that reducers can call other reducers to delegate handling updates for some parts of the state tree they manage.

___
**Total time spent working as an employed developer today**: N/A

**Total time spent practicing code outside of work today**: 1 hour 29 minutes

**Total time spent practicing code outside of work thus far in September 2019**: 20 hours 12 minutes

**Total lifetime hours practicing code outside of a job**: 720 hours 50 minutes

**Total lifetime hours working as an employed developer**: 137 hours 36 minutes