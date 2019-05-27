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
**Total time spent coding today**: 

**Total time spent coding thus far in May 2019**: 

**Total lifetime hours of coding**: 


