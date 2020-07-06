# Monday July 6th 2020 Daily Coding Journal

20:58 -- Here's what I did at the office today:

```
8:00 - 11:45
Daily standup meeting

Caught up on Slack/email

Reviewed team member’s code

Spent some time researching about Node and Express as my team and I had already finished
all of our tasks from the previous sprint.

11:45 - 12:45
Lunch/Nap

12:45 - 17:20
Continued researching about Node and Express

Sprint planning

Started working on the job title task in the React Native project

Resources:
Basic Express Server in Node.js:
https://www.digitalocean.com/community/tutorials/nodejs-express-basics#:~:text=Express%20is
%20a%20web%20application,not%20obscure%20the%20core%20Node.

Notes:

In SemVer, patches is another term for bug fixes, while minors add new features, but neither
break the previous version’s functionality. Majors on the other hand add changes that may not
work with previous versions of the app.

To allow an NPM dependency to update to the latest PATCH version, we can add a tilde (~)
before the dependency’s version in our package.json file.

To allow an NPM dependency to update to the latest MINOR as well as PATCH version, we can
add a caret (^) before the dependency’s version in our package.json file.

Express is a framework for NodeJS that helps us to more easily work with APIs and web
servers.

We can install express using npm install express --save

Express provides us with methods like app.get(), app.post(), and app.put() to tell our application
how to respond. These methods take two parameters. The first parameter is a URL. The second
parameter is a function that takes in a request and a response.

We can use app.listen() and pass it an argument of a port number. This will tell our app which
port to listen on.

We can write and use middleware expressions in Express.

To define a middleware function using express we can use app.use() and pass it a function.

Optionally, we can pass a path as an argument when defining our middleware function. If we do
this, the middleware will only handle requests to that specific route.

By including a call to the next() method at the end of our middleware function, we can tell our
middleware function to continue to the next middleware function (if one exists).
```

20:59 -- I just finished the first section of the FreeCodeCamp APIs and Microservices curriculum (Managing Packages with Npm). Now, I'm moving on to to the Node and Express challenges.

21:12 -- Notes:

- Express evaluates routes from top to bottom.

- We can send files using _res.sendFile(path)_

- JavaScript run in the browser has access to the _windows_ object while Node of course does _not_ have access to the browser's window object. With that being said, Node _does_ have its own globals (technically parameters passed to an IIFE that wraps every JS module file).

- Node provides us with a global called _\_\_dirname_ which will provide us with the name of the directory that the script currently executing resides in.

21:47 -- I'm going to call it a night here. I finished the first 25% of the Node and Express challenges. We'll work to finish the rest of the Node and Express exercises before the weekend.

Ideally, we'd finish the Node/Express exercises before the weekend, and the MongoDB exercises on either Sunday or next Monday.

Then, we'd likely be able to complete the first project in the backend curriculum sometime next week.

But... let's not get ahead of ourselves. We'll take things day by day.

Let's get some rest, and keep up the hustling tomorrow. :))

---

**Total time spent working as an employed developer today**: 8 hours 16 minutes

**Total time spent practicing code outside of work today**: 52 minutes

**Total time spent practicing code outside of work thus far in July 2020**: 7 hours 9 minutes

**Total lifetime hours practicing code outside of a job**: 933 hours 34 minutes

**Total lifetime hours working as an employed developer**: 1759 hours 21 minutes
