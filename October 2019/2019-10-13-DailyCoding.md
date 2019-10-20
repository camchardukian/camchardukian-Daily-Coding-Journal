# Sunday October 12th, 2019 Daily Coding Journal

17:21 — I’m going to be honest, I’m a bit burnt out. I don’t really feel like doing anything right now. However, I’m going to just try to get 30 minutes or so in. Maybe if I feel better I’ll continue past that.

17:28 — I’m spending a little bit of time reviewing selectors in Redux. According to [this article](https://medium.com/@matthew.holman/what-is-a-redux-selector-a517acee1fe8), we can define a selector as:
“…Simply a function that accepts Redux state as an argument and returns data that is derived from that state.

17:29 — Selectors help to keep our Redux store state as simple as possible. 

17:33 — From what I’m reading in this article, selector are used to make our components more simple. Instead of including complex logic in our mapStateToProps() function, we can include that logic in our selectors and then simply insert the selectors into our mapStateToProps() function. 

This can make the logic in our component easier to follow. I’d assume this also means that we can easily reuse selectors to make our code better follow the DRY principle.

17:37 — *Reselect* is the name of a popular library for creating memoized selectors.

17:40 — I’m watching [this video](https://egghead.io/lessons/javascript-redux-colocating-selectors-with-reducers) Dan Abramov created on Selectors. Here are some notes:

— Some developers like to store related reducers and selectors in the same file.

— Selectors are called selectors because they select something from the current state.

17:48 — From what I’ve learned in this session, the reason we use selectors is because we may not want our components to be directly dependent on the state tree. 

I think the reasoner this is because having components directly dependent on the state tree means that if the shape of our state tree changes, we need to change all of the different components that were dependent on the old shape.

Not only is this tedious, but we could easily forget to change all of the components that need changing. This is especially true if we were working on a large application with dozens of components.

Using selectors, however, we’d only need to change a single selector for all of our components to properly interact with the new state tree.

17:52 — Like I said before, I’m a bit burnt out this weekend. I’m going to go the park now, get some exercise and try to relax. While this learning session was relatively short, I now feel as if I have a much better understanding of why we use selectors.

___
**Total time spent working as an employed developer today**: N/A

**Total time spent practicing code outside of work today**: 35 minutes

**Total time spent practicing code outside of work thus far in October 2019**: 10 hours 54 minutes

**Total lifetime hours practicing code outside of a job**: 744 hours 33 minutes

**Total lifetime hours working as an employed developer**: 293 hours 48 minutes