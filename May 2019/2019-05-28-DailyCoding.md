# Tuesday May 28th, 2019 Daily Coding Journal

1:03 -- I just spent a couple minutes getting this coding journal set up. Now let's do a short pomodoro, record the daily developer daily video, edit it, and get to sleep.

P.S. If you were curious, I do **NOT** consider recording videos to be time spent coding.

1:06 -- I've just begun working on building a MEME Generator -- the capstone project in this React course.

1:08 -- Here's the first challenge from the [MEME Generator Capstone Project video](https://scrimba.com/p/p7P5Hd/c6K77um).

```
/**
 * Create the boilerplate to get React to render something on the screen
 * Render an <App /> component, which you'll need to create separately
 */
 ```

 1:10 -- Surprisingly I've had a couple things I had to review here. For example I made the mistake of using REACTDOM.render()instead of ReactDOM.render() amongst other small bugs.

 1:22 -- Working on a strange error that seems to be the result of me importing or rendering something incorrectly:
 >>Error: Unknown require: ../App (in module /index.js) (/index.js:11)

 1:25 -- It seems that one of the errors was that I thought that relative file paths used two dots and a slash. For example:
 > "../MyApp"
 It turns out, however, that only one dot and one slash is needed.
 > "./MyApp"

 1:27 -- Now I'm working on debugging this error:
 >Error: Unknown require: React (in module /App.js) (/App.js:9)

 1:30 -- Oh my goodness. The error I was making was so simple, yet easily overlooked. I accidentally wrote:
 >import React from "React"
 
 instead of writing:
 >import React from "react"

 1:31 -- With that being said, however, I've now finished debugging the first challenge successfully. 

 1:32 -- I'm going to create a new repository on GitHub to make commits to this project on, rather than confuse you by trying to copy and paste the code from all of the different files here.

 1:54 -- Man oh man I'm wiped. I just spent the last 20 minutes or so getting my repo, uploading my project to it, cloning the github repo to my local machine. Well, on the bright side, I've now finished the first challenge in the course, and am ready to hit the road tomorrow morning.
___

11:53 -- Here we goooooooo!

11:54 -- Recall the work I did in the wee hours of the morning? I just looked at the instructor's approach to the problem. We did everything the same except for the fact that his App.js utilized a functional component while mine used a class-based component.

11:56 -- Here's the next challenge for the capstone project:
```
/**
 * Create 2 new components - Header and MemeGenerator
 * Header will only display things
 * MemeGenerator will be calling to an API and holding on to data
 * Each should be in their own file of the same name
 */
```

11:57 -- Before we actually get started coding, let's think about what we have to do. Given that Header will only display things, it seems we could use a functional component.

On the other hand, because MemeGenerator will be calling to an API and *holding on to data*, it's clear that MemeGenerator will need to utilize state and this mandates the use of a class-based component.

12:10 -- Quick thing to note... When we're importing a file into one of our components, the url path appears to be case-sensitive.

12:16 -- I finished the challenge, now I need a few minutes to do *git init* and finish setting up my GitHub repo.

12:38 -- That took waaaaay longer than I expected, but at least I've got my remote and local repos correctly wired up now.

12:39 -- I'm going to watch the instructor's implementation of the previous step, take notes (if anything relevant comes up), commit this journal to GitHub, and then take a short break.

12:43 -- The instructor and I did essentially everything the same for the previous step. By the way, if you'd like to look at my capstone project as it progresses, you can [see it here on GitHub](https://github.com/camchardukian/ReactProjects/tree/master/meme-generator).

12:46 -- The next challenge is so simple, I'll do it now before taking my break! The challenge:
```
/**
 * Initialize state to save the following data:
 *      top text
 *      bottom text
 *      random image (intialize with "http://i.imgflip.com/1bij.jpg")
 */
```

12:48 -- Here's the code I just added to my repo to complete the challenge:
```
this.state ={
topText: "",
bottomText: "",
randomImage: "http://i.imgflip.com/1bij.jpg"
}
```
It looks like we really are babystepping it with this project! ;)

12:55 -- I commited the previous change to GitHub. Now let's see if the instructor and I approached anything differently.

12:56 -- We did everything *exactly* the same except I initialized the state of *randomImage* and he instead chose to use a shorter name of *randomImg*.

12:57 -- This was a great session. I'm going to commit this journal to GitHub, and then continue after a short break.


___
**Total time spent coding today**: 

**Total time spent coding thus far in May 2019**: 

**Total lifetime hours of coding**: 


