# Thursday July 4th, 2019 Daily Coding Journal

22:02 -- It's been a long day. I went to a 4th of July parade and spent some time with lots of relatives that I hadn't seen for 2-5 years.

That ate up the majority of the day. It was fun, and good to see some family members that I hadn't seen since I was still in high school.

With that being the case, let's get to the code! I'm a bit burnt out on the algorithms and data structures.

For that reason, I'm going to spend today and tomorrow learning about Webpack. I figure there's a good chance I'll use Webpack wherever I end up working.

Thus, a baseline level of comfort will speed my onboarding process wherever I get hired. It'll also be good to be able to talk about Webpack intelligently if it comes up in an interview.

I'm going to be taking notes from this [Learn Webpack for Beginners](https://www.youtube.com/watch?v=MpGLUVbqoYQ) video course from Colt Steele.

Here we go!

22:06 -- Here are my notes for Part I (the first 8 minutes or so of the video):
* One of the primary benefits of using Webpack is that it has the ability to take a large number of file types, and bundle them into a smaller group of file types.

* Webpack is very configurable. While this makes Webpack powerful, the high degree of configurability is also the reason Webpack can be a bit intimidating to learn.

* Apart from simply bundling our different files, Webpack is also useful for managing dependencies and ensuring that the code that is supposed to be loaded first is actually loaded first.

* In large applications, our web of dependencies can get very complex, which is why Webpack's ability to manage our dependencies for us is so valuable.

* *webpack_require_* is how Webpack keeps track of where things should be imported and exported (which is basically how Webpack manages our dependencies).

22:22 -- We're finished with part I! I'm going to get a little exercise, and then we'll get to part II.
___
23:13 -- Alright I'm back. Let's get another 40 or so minutes of code in today.

Here are my notes for part II of the [Learn Webpack for Beginners](https://www.youtube.com/watch?v=MpGLUVbqoYQ) video course from Colt Steele:
* Colt has been demonstrating what it would look like to manage dependencies without Webpack.

Basically, he's stressing the point that managing the dependencies of a React app with dozens, or even hundreds of components, each with their own dependencies would be a total nightmare.

* To install Webpack, the first thing we need to do is set up our package.JSON. We can do this using the command:
> npm init -y

* The next thing we want to do is install Webpack and Webpack's command line interface. We can do this using the commands (Note: sometime this step can take several seconds, or minutes to reach completion):
> npm install --save-dev webpack webpack-cli

* By default even before choosing anything for yourself, Webpack has some default values.

UPDATE: I was able to reach all the way to the 18th or so minute in this video course. In tomorrow's journal entry, we'll try to finish going through the course.

___
**Total time spent coding today**: 46 minutes

**Total time spent coding thus far in July 2019**: 10 hours 47 minutes

**Total lifetime hours of coding**: 661 hours 7 minutes