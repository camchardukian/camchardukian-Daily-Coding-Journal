# Friday November 22nd, 2019 Daily Coding Journal

21:00 — Today I purchased Bob Ziroll’s *React Bootcamp* course on Scrimba. His *Learn React for Free* course was great for learning the basics of React so I’m hoping going through his new course will make me a more productive developer at the office.

I’ll try taking notes on pretty much every video on the course (besides the intro video and possibly some other rare exceptions). Let’s get started! 

## **Video #2: Setting the Stage with Modern JavaScript Features:**

— We no longer *need* to use constructors to use state inside of class methods in React.

— When destructuring, we can actually rename the property that we’re using by adding a colon. Here’s some example code below…

```
const { greeting: hello  } = this.state
```
We would then use *hello* in our return statement rather than *greeting*. I don’t see a whole lot of utility in doing this, but I’m sure there are some edge cases where this functionality could make our code more readable.
___

## **Video #3: React.Fragment:**

— We can prevent pollution of the DOM tree by wrapping our JSX children elements with React Fragments rather than always using div tags.

— Here’s an important caveat when converting div elements into React Fragments… Because React Fragments do not display in our HTML while div elements do… using React Fragments instead of divs (or vice versa) can impact the CSS we’ve already written.
___

## **Video #4: Default Props:**

— The purpose of default props is basically to cover ourselves in the situation that we or another developer on our team forgets to pass a prop to some function/component, or if we simply want our function/component to have some props by well… default.
___

## **Video #5: Prop Types:**

— Prop Types are a useful development tool because we will receive reminders in the form of warnings when a component receives a prop that is not of the same type the developer intended for that component to receive.

— It’s possible to require our prop is limited to only being passed certain values.

Here’s some example syntax from the [React docs](https://reactjs.org/docs/typechecking-with-proptypes.html#proptypes):

```
PropTypes.oneOf([’News’, ‘Photos’])
```

— Here’s a nuanced point regarding prop types… If we set a prop as being required, but also set a default value for that prop… In the event the developer does not pass a value for that prop, no warnings will be displayed.

This is supposedly because under the hood, React is simply evaluating whether a prop has been passed some value and does not give any importance to where that value came from.
___
21:46 -- Only 45 or so minutes in and I've already learned some pretty cool information in this course. I'm excited to continue going through this course this weekend.

Before getting to bed, let me quickly show what I did at the office today:
```
7:50 - 8:00
Connected keyboard.

Connected mouse.


8:00 - 11:45
Scrum meeting.

Caught up on Chatwork/email

Continued working on company register page part II.

11:45 - 12:45
Lunch/nap

12:45 - 5:20

Had a meeting with the company director.

Finished working on company register feature

Resources:
https://material-ui.com/components/chips/

Notes:
When using Material-UI chips, we need to use the React useState hook to change the values in our form field rather than trying to change the values directly.
```
21:48 -- Today has been a solid day. Let's get some sleep, hit the gym hard tomorrow morning, and make this a great weekend!
___
**Total time spent working as an employed developer today**: 8 hours 12 minutes

**Total time spent practicing code outside of work today**: 1 hour 20 minutes

**Total time spent practicing code outside of work thus far in November 2019**: 18 hours 11 minutes

**Total lifetime hours practicing code outside of a job**: 782 hours 35 minutes

**Total lifetime hours working as an employed developer**: 537 hours 16 minutes