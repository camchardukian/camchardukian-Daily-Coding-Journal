# Friday July 5th, 2019 Daily Coding Journal

0:19 -- When we start coding tomorrow, we'll continue taking notes from [part II of this learn Webpack course](https://www.youtube.com/watch?v=MpGLUVbqoYQ).
___

11:53 -- Back to taking notes on Part II of the Webpack course...

* Webpack doesn't just add or append the JavaScript we've written to the end of our *main.js* file. Webpack actually wraps our code inside of "Webpack code" to perform some different "Webpack" magic on the code we've written.

* When we create a project using Webpack, we can add a few files to *.gitignore*. Neither *node_modules* nor *dist* need to be committed to GitHub.

This is because they would take up unnecessary space, and could both be easily derived from the rest of our code.

By running *npm install* we can get *node_modules*, and by running *npm start*, Webpack will build *dist* using *main.js*.

12:06 -- I've finished Part II. Now, I'm going to say goodbye to my Aunt because I probably won't see her again for another 1-2 years.

I'll also commit this journal entry to GitHub, and go through my morning routine.

Then, we'll tackle Part III of this course, which is about 'Imports, Exports, & Modules'.

See you later!
___
13:07 -- On to Part III. Here are my notes:

* I didn't take a lot away from Part III that I didn't already know. This part of the course mostly talked about ES6 imports and exports.

This is a topic I already had a pretty solid understanding of thanks to Bob Ziroll's [Learn React for Free](https://scrimba.com/playlist/p7P5Hd) course.

Basically, I just reviewed the concept that by taking advantage of imports and exports, we can influence the order in which our code is run, and make things look cleaner in our *index.js* and *main.js* files.

13:19 -- Let's push through and try to take notes on Part IV of this course.

Part IV is about **Configuring Webpack**. Here are my notes:

* Webpack has some different "settings" set by default. For example, the default place Webpack looks for an entry point is *index.js* (by entry point, I believe the course creator is talking about where Webpack will begin "getting to work"). By default, Webpack also puts the code it "gathers" into our *main.js* file.

* To change default behaviors, or add plugins or loaders, we need to make a config file.

* Inside of our config file, we'll create an object that has several properties. I'm honestly having a bit of trouble understanding this part of the video.

For that reason, I'm going to get some rest and during my next coding session I'll try to take better notes on what to do inside of our config file.

See you then!
___


___
**Total time spent coding today**: 

**Total time spent coding thus far in July 2019**: 

**Total lifetime hours of coding**: 