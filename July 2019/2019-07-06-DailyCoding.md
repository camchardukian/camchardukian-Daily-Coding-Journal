# Saturday July 6th, 2019 Daily Coding Journal

10:57 -- I'm back. Let's finish taking notes on Part V of the [Colt Steele Learn Webpack course](https://www.youtube.com/watch?v=MpGLUVbqoYQ).

I think I'll try formatting my notes a bit differently today. Instead of doing bullet points again I'll instead just write the note along with the time I took it.

Just for a change of pace.

11:01 -- We can install Bootstrap locally on our machine using the following command:
> npm install --save-dev bootstrap

11:06 -- There is a loader called the *sass-loader* that will load a Sass/SCSS file and compile it into regular CSS.

It's important to note, however, that using this loader requires installation of 2 packages: *sass-loader*, and *node-sass*.

11:10 -- Creating a "dev-server" can ease the development process because it will allow Webpack to recognize any changes we make any automatically rebundle all of our assets.

11:12 -- I just finished Part V of the course! Now, I'm going to commit this journal entry to GitHub, take a 10-15 minute break, and then continue on with part VI of the course!
___

11:34 -- Mom came home. Helping with some groceries, will chat a little, go through my morning routine and then be back in an hour or so.

12:52 -- I'm back. Let's start part VI 'Cache Busting & Plugins'.

12:55 -- Cache busting is a way of preventing browsers from caching assets that we don't want to be cached.

12:56 -- A cached file is basically a file that the browser "remembers" and already has a copy of locally.

Because of this, the browser will often opt to use the file it already has access to locally rather than trying to pull a file from the server that may or may not have received any updates since the last time the file was cached.

13:00 -- If everytime we bundle our code using Webpack, it's very possible the browser will attempt to cache our code if the name of our file doesn't change.

For that reason, we want the name of our file to change whenever any of the contents of that file change.

We DON'T want to update everything on our website, but have our users unable to view these updates because they already have files from our website cached.

Sure, some internet users may be savy enough to clear their cache if they are anticipating an update, but this is far from ideal and certainly not the norm.

Fortunately, we can use something called a "content hash" which basically changes the name of the file into what appears to be a series of random characters, but is actually produced using a hashing function (often md5).

This gives us a slightly different file name whenever we make ANY change to our file, and thus forces the user's computer to NOT rely on their cache, but instead request the updated data from the server!

This entire process can be referred to cache busting.

13:08 -- Taking a step back, let's think about what types of files we'd want the browser to cache, and which files we should perform cache busting on.

The answer is pretty simple actually. If a file is expected to change frequently, or any changes it may have are of significant importance to our application, we should use cache busting.

If we're ok with using older versions of a file, as perhaps is the case with JavaScript libraries for example, we can allow the browser to cache said file in order to optimize load times.

13:11 -- Next, we're going to start learning about plugins. Here's what the official Webpack documentation says about plugins:
> The *plugins* option is used to customize the webpack build process in a variety of ways. Webpack comes with a variety of built-in plugins available under *webpack.[plugin-name]*

13:14 -- My focus is pretty poor today because I'm running on low sleep. I'm going to commit this journal entry to GitHub, do some chores, take a nap, and then finish part VI later.
___
17:38 -- Got some sleep, did some laundry, ate lunch, etc. Now, let's finish taking notes on part VI.

17:40 -- Webpack has hundreds of different plugins.

17:41 -- Let's talk about the *HtmlWebpackPlugin*. Here's the official explanation from the [documentation](https://webpack.js.org/plugins/html-webpack-plugin/):
> The *HtmlWebpackPlugin* simplifies creation of HTML files to serve your webpack bundles. This is especially useful for webpack bundles that include a hash in the filename which changes every compilation. You can either let the plugin generate an HTML file for you,supply your own template using lodash templates, or use your own loader.

17:54 -- We can install the *HtmlWebpackPlugin* with the following command:
> npm install --save-dev html-webpack-plugin

18:00 -- If we want to use a template with the *HtmlWebpackPlugin* we can do so using the following code:
```
plugins: [
    new HtmlWebpackPlugin({
        template: ".pathHere/htmlFileNameHere"
    })
]
```
Of course, obviously the value you give to the template property would contain an actual path to an actual HTML file.

18:04 -- We're now finished with part VI of the [Colt Steele Learn Webpack course](https://www.youtube.com/watch?v=MpGLUVbqoYQ).

18:05 -- I'm going to commit this journal entry to GitHub, and then try to knock out the first half of part VII.
___
18:09 -- Alright, just finished committing things to GitHub. Now, let's get started with part VII!

18:10 -- Often, we may want our developmental application and consumer/client application to have different features or functionality.

For example, we may want our dev mode application to have a live server which would allow us to more efficiently write and test our code.

On the other hand, we may want our live application to use minified files to speed load times for consumers/clients.

18:20 -- Remember how we just talked about having a live server above? Here's the code we could include inside of our *package.json*
```
"scripts": {
    "start": "webpack-dev-server --config webpack.dev.js --open
}
```
While I think some of the above code could change depending on what we named our dev server (I think, but I'm not sure that our dev server could be named anything), most important is the fact that we include --open, which will open up a window in our browser whenever we save our webpack project.

18:26 -- During my next coding session I'll tackle part VIII -- HTML-Loader & File-Loader.

Clearly we live in exciting times hahaha.
___
19:48 -- Got a little bit of exercise in. Now, let's talk about HTML-LOADER & FILE-LOADER.

20:03 -- I felt this part of the course was a bit confusing. For that reason, I'm going to take notes from some supplementary videos.

20:04 -- [Supplementary video #1](https://www.youtube.com/watch?v=GSUP1zK7aXA) notes:

* Webpack doesn't know every programming language. It only "knows" JavaScript.

* Webpack relies on different loaders to "understand" code from other programming languages or file types.

* Loaders run in the reverse order that they are written. In other words, the loaders written last (closer to the bottom of your file) will actually be processed first, and Webpack will then work through the loaders sequentially going upward.

20:11 -- [Supplementary video #2](https://www.youtube.com/watch?v=8DDVr6wjJzQ) notes:

* An entry point is where Webpack will start looking for dependencies. A Webpack project can have multiple entry points.

* The term output refers to where Webpack should store the bundle(s) it creates.

* Module loaders allow us to transform our code.

20:21 -- Getting back to the Colt Steele course, we can install a plugin called *clean-webpack-plugin*, which will delete or "clean up" the *dist* directory everytime we build our application.

This prevents a lot of clutter from accumulating in the *dist* directory.

20:24 -- During my next coding session, I'll take notes on part IX of Colt's course.
___
21:39 -- I'm back. Let's take some more notes.

21:48 -- This part talked about *vendor.js*. From my limited understanding, it looks like the point of having a *vendor.js* file is to store files that rarely change such as JavaScript libraries and other less frequently updated dependencies such as BootStrap.

We can then cache *vendor.js* while still updating our *main.js* with some frequency.

21:53 -- I'm feeling a bit burnt out on coding everything alone. I'm still keeping with it to some extent, but I'm definitely hoping to join a team and work on some real projects soon.

21:55 -- My family just got home from dinner so I'll probably hang out with them a bit before my brother goes back to Milwaukee.

With that being said, I'll try to finish the rest of this Webpack course tonight.
___
22:39 -- I'm back. Let's go, Part X -- 
[Extract CSS & Minify HTML/JS](https://www.youtube.com/watch?v=MpGLUVbqoYQ).

22:41 -- For performance reasons, it can be beneficial to have a separate CSS file rather than having to wait for JavaScript to inject CSS into our HTML.

22:48 -- We can minimize our CSS using the *optimize-css-assets-webpack-plugin* plugin.

22:53 -- We can minimize our HTML file using *HtmlWebpackPlugin* and using the *minify property*, and passing it an object that has the following properties all set to true:
*removeAttributeQuotes*, *collapseWhitespace*, *removeComments*.

22:55 -- Here's the actual code for what we were just dicussing above about minimizing our HTML:
```
new HtmlWebpackPlugin({
    minify: {
        removeAttributeQuotes: true,
        collapseWhitespace: true,
        removeComments: true
    }
})
```
23:02 -- I just finished Colt Steele's Learn Webpack course. If I'm being honest, I'm still not super comfortable with Webpack.

With that being said, I no longer feel as if I'm going to be panicking if I have to work on some project that requires me to interact with Webpack.

It's also good to know that for the most part, we really only need to setup Webpack once per project.

That, along with the fact that I may be on a team of developers working with Webpack means that being a Webpack master right out of the gate when I start working probably isn't absolutely necessary.

With all of this being said, I'm glad I went through this course, and spent 6-8 hours (or however many hours it ended up being) getting comfortable with Webpack.

23:07 -- I think that tomorrow I'll work on building a reponsive, mobile first website using HTML 5 and CSS3.

I think I should review those skills as I've pretty much been focusing on JavaScript and React these last 6 months.

23:08 -- See you tomorrow!

___
**Total time spent coding today**: 3 hours 10 minutes

**Total time spent coding thus far in July 2019**: 16 hours 31 minutes

**Total lifetime hours of coding**: 666 hours 51 minutes