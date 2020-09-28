# Monday September 28th 2020 Daily Coding Journal

20:00 -- Today was a solid day, here's what I did at the office:

```
8:00 - 11:45
Daily standup meeting

Caught up on email/slack

Read documentation

Sprint planning

11:45 - 12:45
Lunch/Nap

12:45 - 17:00
Added some new fields to the register flow

Fixed some UI bugs in the post image gallery when displaying more than 4 pictures

Resources:
Reconciliation: https://en.reactjs.org/docs/reconciliation.html

Pure Component & React.memo:
https://medium.com/takeaway-tech/a-deep-dive-into-pure-component-and-react-memo-and-why-do-we-need-them-ae99dce6a33c

Notes:
Reconciliation is the process React uses to see which parts of the DOM should be updated.

React.memo is similar to React.PureComponent, but React.memo only checks for changes in props (rather than checking props and state like React.PureComponent).

We use React.PureComponent for class components whereas we use React.memo with functional components.

React.memo takes a 2nd argument “areEqual” where we can write our own comparison logic, if we don’t want to use the default comparison logic.
```

20:02 -- After work I also spent an hour reading _Pro Git_ as well as taking notes/experimenting in the terminal.

Today I learned some new things about stashing in Git. In addition, I was exposed to _git clean_ and signed commits using GPG for the first time.

In any case, I'm pretty tired now so I'm going to call it a night. See you tomorrow!

---

**Total time spent working as an employed developer today**: 8 hours 1 minute

**Total time spent practicing code outside of work today**: 1 hour 2 minutew

**Total time spent practicing code outside of work thus far in September 2020**: 11 hours 55 minutes

**Total lifetime hours practicing code outside of a job**: 987 hours 27 minutes

**Total lifetime hours working as an employed developer**: 2226 hours 24 minutes
