# Monday September 23rd, 2019 Daily Coding Journal

19:39 — Today was a bit of a difficult day at work. It seems like every time I start feeling like a semi-decent developer, I end up moving on to a new task and feeling lost again. Here’s what my day at the office looked like today:
```
7:50 - 8:00
Connected keyboard.

Connected mouse.

8:00 - 9:00
Scrum meeting.

Answered some of new team member’s questions and introduced him to other developers and HR.

Caught up on Chatwork/email.

Started designing UI for block connections page.

9:00 - 11:45
Continued working on UI for block connections page

11:45 - 12:45
Lunch/nap

1:00 - 5:00
Continued working on UI for block connections page
```

In any case, my team leader thinks I need to review some of the ReactJS basics.

So, I’m going to put finishing that Postman course on hold and instead take notes on [this article](https://reactjs.org/tutorial/tutorial.html#lifting-state-up) tonight.

19:51 — I’ve spent the last several minutes creating a new react app, and configuring it to follow along with this tutorial. I decided I might as well go through this whole article rather than just looking at the small subsection my team leader showed me.

19:55 — When we write a JSX element such as a *<div \/>* tag, what’s really happening under the hood is React is running *React.createElement(‘div’)* at the time we actually “build” our app.

20:06 — I’ve mostly just been following the tutorial the last 10 minutes. No big epiphanies yet. Just getting some extra practice thus far.

20:10 — This piece of information seems important:
> When you call *setState* in a component, React automatically updates the child components inside of it too.

Basically, my interpretation of this is that if our parent component’s state changes, all of the child components that used or inherited some state value from the parent will be updated/re-render. 

20:13 — Here’s another important concept — parents can pass state down to their children using props.

It’s recommended that if we have two child components that need to communicate with each other, that we declare the shared state in their parent component.

While I understand the first concept, I’m still kind of shaky on the second one. I understand the second one on a pseudo intellectual level, but I cannot yet explain why it is true.

20:17 — My neck hurts a little bit. I’m going to take a 10 minute break to clean, and find something to eat. Be back around 20:30.

20:26 — UPDATE. I just ordered some food to save time from having to go to the restaurant.. I’m going to do a quick 20 minutes or so of exercise because my body feels sore from sitting all day.

20:52 — I’m back. Let’s get another 15-20 minutes of learning in before the food arrives.

21:28 — So… I actually only got about 6-7 minutes of coding in before the food came. On the bright side, I finished eating already and got a nice walk around the neighborhood in too.

Now, I’m going to focus on this project with no distraction for a minimum of 30 minutes.

21:40 — Let me try to explain the concept I’ve spent the last several minutes meditating on. If we have a parent component, we can give that parent a prop. The prop could be called value, or firstName, or anything really.

Now, when we put our original parent component and nest it inside another component, what was once the parent component now becomes a child component.

That child component can then use the prop that we defined in the parent component. For example, our parent component could look something like this:
```
printName(name) {
return <nameComponent value={name}
```
Then, in our nameComponent… we could use the name prop from the printName method we defined earlier…

Well, now that I tried explaining, it seems my understanding still isn’t up to the level it needs to be. But, I think if you read my explanation you’ll see that I’m *kinda* getting the point.

21:56 — Controlled components are components that are fully controlled by another component.

22:05 — Immutability and avoiding mutations is an important concept in React. There are several reasons we should steer away from mutations:

— By avoiding mutations we can more easily detect whether an object has changed.

— Immutability can make some features such as a user’s history intact and usable at a later time.

— Immutable data can easily determine if changes have been made which helps us to determine when a component requires re-rendering. In other words, we can use pure components and optimize our app’s performance.

22:20 — I just finished the tutorial. I’m going to take a quick break, and then I think I’ll take notes on one video about props to solidify my knowledge and because I think my understanding of this subject will benefit a lot from a more visual explanation.

22:44 — I just finished watching [this video](https://www.youtube.com/watch?v=GIU8ekYndKw) on props. It was a nice review, and the video also taught me about a special property in react that allows us to pass entire blocks of code.

That special property is *this.props.children*.

23:00 — Having GitHub problems with my tic-tac-toe project… sigh…

NOTE TO SELF: Keep this response from GitHub when you have the problem again:
```
Git thinks it's a submodule as it has a .git directory inside it. To fix...
Changed directory to the offending dir:
cd <offending git submodule>
Remove the .git directory inside it:
rm -rf .git
Update the git cache:
git rm --cached <offending git submodule>
Go to the parent directory:
cd ..
Add the directory to git:
git add .
git commit -m "Changed submodule to directory"
git push --all

```
23:07 — Well I’m beat and it’s time to head to bed. I’m going to commit this entry and then quickly go through my evening routine so I can get some sleep and be ready for tomorrow.

___
**Total time spent working as an employed developer today**: 8 hours 18 minutes

**Total time spent practicing code outside of work today**: 2 hours 17 minutes

**Total time spent practicing code outside of work thus far in September 2019**: 27 hours 17 minutes

**Total lifetime hours practicing code outside of a job**: 727 hours 52 minutes

**Total lifetime hours working as an employed developer**: 178 hours 24 minutes