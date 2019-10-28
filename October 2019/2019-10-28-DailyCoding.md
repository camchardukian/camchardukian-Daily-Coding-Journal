# Monday October 28th, 2019 Daily Coding Journal

18:54 -- While it's an "early" end to the day, I've worked really hard today. Here's what my day at the office looked like:
```
7:50 - 8:00
Connected keyboard.

Connected mouse.

8:00 - 11:45
Scrum meeting.

Caught up on Chatwork/email

Familiarized myself with the new KOREC project.

Started working on login page UI

11:45 - 12:45
Lunch/nap


12:45 - 5:45
Finished login page UI and also added functionality to the page.

Notes:

— Normally our component will re-render anytime our state or props change. If our component needs re-rendering in some other unique circumstance, however, we can inform the component that it needs to be re-rendered by calling forceUpdate(). While forceUpdate() can sometimes be useful, we should use it only necessary and instead rely mostly on state and props to trigger re-rendering.

— In React, portals allow an element to continue to inherit properties as it normally would, but be rendered in a position outside of its parent component’s DOM node.

— static getDerivedStateFromProps() is invoked in both the the mounting and updating phases of the React Lifecycle.

— Fields in Redux-Form have a required components prop.

Resources:

React Lifecycle Methods Description and Sequencing: 
https://blog.logrocket.com/the-new-react-lifecycle-methods-in-plain-approachable-language-61a2105859f3/

Portals in React:
https://medium.com/@siobhanpmahoney/portals-in-react-js-5d98bb89797c

How to Center Absolutely Positioned Elements:
https://stackoverflow.com/questions/1776915/how-to-center-absolutely-positioned-element-in-div
```
18:55 -- After work, I also read another chapter of *The Art of Readable Code*. Here are my notes from chapter 3:
```
The key idea Boswell & Foucher open this chapter with is that developers should strive to:

Always scrutinize your names by asking yourself, “What other meanings could someone interpret from this name?”

Basically, it seems to me that the main idea the authors are trying to impart on us is that we should avoid ambiguity and anything that could possibly be misinterpreted when naming things as a developer.

I like the first example they give in this chapter of a function named filter(). The authors say that filter is an ambiguous word because it’s difficult to know whether our usage of said function is to help us choose something, or get rid of something.

For that reason, the authors propose two better possible names for this hypothetical function.

In the authors’ words,

If you want “to pick out,” a better name is select(). If you want “to get rid of,” a better name is exclude().

— The Art of Readable Code

— Instead of using the words start and stop to indicate a range, it may be clearer to use the parameter names begin and end.

— When naming booleans we should be conscious to avoid negative terms in our names. disableSecurityMode is a variable name that is not immediately clear about what it is doing (you may need to spend several seconds conceptually thinking about what a value of true would mean).

— The words is and has can also be used in our variable names to indicate that our variable is indeed a boolean.

— We should be conscious of naming our functions to clearly indicate to other developers whether the usage of said functions would be resource intensive and have a significant effect on performance.

The function names getAverageEmployeeSalary and computeAverageEmployeeSalary clearly give different first impressions about how many resources firing the function would command.
```
If you'd like to view the notes more cleanly formatted, [click here](https://github.com/camchardukian/Software-Development-Book-Notes/blob/master/The%20Art%20of%20Readable%20Code/Chapter_3-Notes.md).

19:00 -- Anyway, I'm pretty fatigued now and my back is sore. See you tomorrow!
___
**Total time spent working as an employed developer today**: 8 hours 4 minutes

**Total time spent practicing code outside of work today**: 1 hour 25 minutes

**Total time spent practicing code outside of work thus far in October 2019**: 26 hours 33 minutes

**Total lifetime hours practicing code outside of a job**: 760 hours 13 minutes

**Total lifetime hours working as an employed developer**: 382 hours 59 minutes