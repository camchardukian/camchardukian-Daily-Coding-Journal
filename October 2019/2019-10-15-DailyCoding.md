# Tuesday October 15th, 2019 Daily Coding Journal

21:30 -- Here are some notes I just finished taking on Lifecycle methods in React:

-- Lifecycle methods allow us to implement some types of functionality at different stages of React building or rerendering our application.

-- *componentWillMount* runs when our component is about to be put on to the screen.

-- Then, our component will be rendered.

-- After our component is rendered, *componentDidMount* will run.

-- *shouldComponentUpdate* runs immediately after we set state to some value.

-- If *shouldComponentUpdate* returns true, *componentWillUpdate* will then run.

-- Then our component will be rerendered.

-- Finally, *componentWillUpdate* will run.

-- We should never set state inside of our render method. The reason for this is that setting state will cause another rerender. This could easily lead into an infinite loop.

The reason we should never set state directly (i.e. without using *setState*() or Redux) is that setting state directly will prevent our application’s componentDidUpdate from being aware of the changes that have occured to our state.

21:33 -- Here's what my day at the office looked like today:
```
7:50 - 8:00
Connected keyboard.

Connected mouse.

8:00 - 11:45
Scrum meeting.

Caught up on Chatwork/email

Fixed bugs about profile page UI and basic information page.

11:45 - 12:45
Lunch/nap

12:45 - 5:10
Continued fixing bugs on basic information page, and started fixing bugs on bio page.

Notes:

Resources:
```
21:35 -- While I felt pretty good about my performance at work yesterday, today I felt pretty bad.

Despite working on trying to fix these bugs for basically 9+ hours now, I haven't made a whole lot of progress.

My team lead hasn't gotten angry at me, but of course I'd like to be doing better. With only two real days of work left before the end of sprint meeting, I have no idea what's going to go down these next two days considering I have something like 12 tasks in Jira waiting to be completed lol.

Oh well, with not a lot of time left on my trial contract, I'll just keep doing my best and hoping that my contract gets extended.

No matter what happens, however, I feel great knowing that I'm waaaay further along in my development journey than I was just two months ago.

My skills have improved a TON in the last two months. In any case, I'm going to get ready for bed tomorrow, and hopefully do better tomorrow.

___
**Total time spent working as an employed developer today**: 8 hours 12 minutes

**Total time spent practicing code outside of work today**: 50 minutes

**Total time spent practicing code outside of work thus far in October 2019**: 11 hours 52 minutes

**Total lifetime hours practicing code outside of a job**: 745 hours 32 minutes

**Total lifetime hours working as an employed developer**: 310 hours 6 minutes