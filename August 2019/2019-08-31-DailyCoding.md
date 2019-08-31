# Saturday August 31st, 2019 Daily Coding Journal
12:39 — I just finished teaching an English class. It’s a good way to make short-term $$$ while I improve my coding skills. Anyway, now I’m going to start a new React project. I’m going to design a couple components in React, and then attempt to connect them using React-router.

12:49 — There are three different packages of React Router available for installation: react-router, react-router-dom, and react-router-native. Generally speaking, you won’t need to install react-router directly. This is because both react-router-dom and react-router-native re-export all of react-router’s exports.

12:52 — Because I’m looking to build a website, it seems that installing react-router-dom will be the most suitable. The command for installing react-router-dom is:
```
npm install —save react-router-dom
```

12:53 — For browser based projects (like a website), there are two different types of routers we can use. Those two types are:

\<BrowserRouter> — Should be used when our server will handle dynamic requests.

\<HashRouter> — Should be used when our website is hosted on a server that only handles static files.

___

20:15 — I’m currently installing react-router-dom to use in my project. I’m not sure how much programming I’ll be able to get in tonight as I promised my girl we’d spend a little time to relax and watch a move or play a game tonight. But… she hasn’t come back yet so I’ll try to get a little work in!

20:17 — After installing react-router-dom using the command I mentioned earlier (npm install —save react-router-dom) you should be able to see react-router-dom in your list of dependencies in your package.json file.

20:19 — To actually use the <BrowserRouter> tag in our app, we need to import it from react-router-dom.

One cool thing I learned today is that we can import components/things under a different name by using the “as” keyword.

For example, instead of saying import {BrowserRouter} and having to use the <BrowserRouter> tag in our project, we can instead import {BrowserRouter as Router}.

This allows us to instead use the (arguably) cleaner looking \<Router> tag in place of the default \<BrowserRouter> tag.

20:57 -- I got some good practice in tonight. I wish I could do more, but now it’s time to chill our after logging 50+ hours of programming in a single week for the first time in my life (along with another 5ish hours of teaching English)!

20:58 — I made a TON of progress this week! I can’t wait to learn more about react-router tomorrow!

___
**Total time spent working as an employed developer today**: N/A

**Total time spent practicing code outside of work today**: 1 hour 25 minutes

**Total time spent practicing code outside of work in August 2019**: 20 hours 54 minutes

**Total lifetime hours practicing code outside of a job**: 700 hours 34 minutes

**Total lifetime hours working as an employed developer**: 67 hours 10 minutes