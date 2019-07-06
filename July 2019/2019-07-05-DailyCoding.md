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
20:08 -- I'm back. Let's continue our notes on Part IV:

* The config file could be called just about anything we'd like it to be, but a fairly standard naming convention is to call it *webpack.config.js*. 

* The entry property is used to determine where we should enter, or have Webpack begin "doing its job". Webpack can be configured for our application to have either one or many entry points.

* According to the [official documentation](https://webpack.js.org/concepts/output/), the output property tells Webpack where to write the compiled files to the disk. In other words, it seems that we can use the output property to say where we want our file to be saved after Webpack finishes "building" whatever it needs to build or do.

* We can also control the name of the saved file using the *filename* property inside of our *output* object.

* Most importantly, we also need to tell Webpack **where** to "spit out" this saved file. We can do this using the *path* property and giving this property a value of *path.resolve(__dirname, "ChooseYourDirectoryNameHere")*. The reason we need to use *.resolve* and *__dirname* is because the directory we are currently in on our machine is likely different than the directory someone would be inside of on another machine.

* *__dirname* is used to determine whatever directory the user is inside of on their machine, which then allows us to save our directory containing our file inside of that directory.

* Inside of our *package.json* file, we'll want to include the code
```
"scripts": {
"start": "webpack -- config webpack.config.js"
}
```

* The above code tells *package.json* to run Webpack starting with the configuration file. Of course, if you named your configuration file something different you wouldn't write *webpack.config.js*, but you'd use whatever you called your configuration file.

* Webpack runs in production mode by default. We can change this by using the *mode* property and giving it a value of *"development"*.

* Inside of our config file we can also decrease/eliminate the frequency of "debuggingish" code blocks occuring in our saved file by setting the *devtool* property to *"none"*. While I'm not whether this is ever absolutely necessary, it is possible.

20:57 -- I just finished taking notes on Part IV of Colt Steele's Learn Webpack course. During my next coding session I'll move on to taking notes on Part V of the course.

___
**Total time spent coding today**: 

**Total time spent coding thus far in July 2019**: 

**Total lifetime hours of coding**: 