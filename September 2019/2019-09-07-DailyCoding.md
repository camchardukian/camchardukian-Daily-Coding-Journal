# Saturday September 7th, 2019 Daily Coding Journal

7:40 — I woke up early today to get an hour or so of coding in before teaching my English class. Normally, I’d have been able to get two hours of programming in during this time, but today I’m going into work an hour early to do some small event at the center.

7:53 — It turns out that the reason I was getting a bunch of bizarre errors from ESLint in my Haunted-House (react-router-practice) application last week was that apparently ESLint doesn’t know our application is a React app by default.

It seems for ESLint to run properly we need to install an ESLint plugin that’s specific to React, along with editing some lines in our ESLint config file and package.json file.

8:10 — If you’re trying to set-up a React application that uses ESLint, I highly recommend referring to these two articles:

1. [Setting up ESLint in React](https://medium.com/@RossWhitehouse/setting-up-eslint-in-react-c20015ef35f7)
1. [Setting up ESLINT in your JavaScript Project with VS Code](https://medium.com/@dammak/setting-up-eslint-in-your-javascript-project-with-vs-code-264dcaf1f410)

8:24 — I finally finished creating my React application and getting ESLint setup properly (UPDATE: Or so I thought lol). It was a little slow this first time around, but I now know how to do it :D

I’m sure each time I go through this process I’ll get faster and faster. :))

8:31 — I just learned how to configure different rules in ESLint. Apart from the defaults, I also added the “indent” rule to enforce cleaner indentation and cleaner looking code :D

I just had to add:
```
"indent": "warn"

```
inside of rules in my .eslintrc.json file. Now, it looks like this:
```
    "rules": {
        "indent": "warn"
    }

```
8:44 — I’m having some bugs with unreachable code behavior in my application. I’m not sure why as I’ve never had this problem before. Unfortunately, I have to go to work now so I’ll look into it more later.

19:36 — Even…

20:05 — I’ve spent the last 30 or so minutes trying to solve this last bug. I still don’t know how to solve it to be honest. I’ve gotten my app to run, but am still dealing with some errors.

20:07 — With that being said, I just spent the last few minutes reading about *npm audit*, and *npm audit fix*.

20:13 — I’m still lost. Can’t figure it out, I’ll try again tomorrow, or maybe just practice something else, and ask another developer from work to teach me how to do it.

___
**Total time spent working as an employed developer today**: N/A

**Total time spent practicing code outside of work today**: 2 hours 11 minutes

**Total time spent practicing code outside of work thus far in September 2019**: 11 hours 51 minutes

**Total lifetime hours practicing code outside of a job**: 712 hours 27 minutes

**Total lifetime hours working as an employed developer**: 99 hours 26 minutes




























































