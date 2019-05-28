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
13:12 -- We gon' be hardcore today. Let's get back at it!

13:13 -- The challenges are starting to get a bit more challenging now. Here's the next challenge:

```
/**
* We'll be using an API that provides a bunch of meme images.
* 
* Your task:
* make an API call to "https://api.imgflip.com/get_memes" and save the 
* data that comes back (`response.data.memes`) to a new state property
* called `allMemeImgs`. (The data that comes back is an array)
*/
```
13:14 -- If I'm being perfectly honest, I do not remember too much about making API calls. I believe we need to use the *fetch* method and provide a URL but beyond that I'm not sure.

For that reason, I'm going to spend a few minutes reviewing the API material covered earlier in this course.

13:23 -- I just spent the last several minutes watching a [video about Fetching Data from an API](https://scrimba.com/p/p7P5Hd/c79Jask).

13:27 -- Thus far I've created a componentDidMount() method and created a new property called allMemeImgs and initialized it to an empty array.

13:29 -- It looks like the next thing I'm going to need to do is use the fetch method and resolve the resulting promise.

13:33 -- Here's the code I've been working on for the last few minutes:

```
class MemeGenerator extends Component {
constructor() {
    super()
    this.state = {
        topText: "",
        bottomText: "",
        randomImg: "http://i.imgflip.com/1bij.jpg",
        allMemeImgs: []
    }
}

componentDidMount() {
    fetch("https://api.imgflip.com/get_memes")
    .then(response => response.json())
    .then(data => {
        this.setState({allMemeImgs: data})
        console.log(this.state.allMemeImgs)
    })
}
```
Why is there a console.log() method you ask?I included it to verify that I successfully set the state of allMemeImgs to the data we received from the API.

I can confirm to you that everything was successful! :)

13:36 -- Added a comment to my code explaining why I included a console.log() method.

13:37 -- I'm going to commit my project to GitHub and then see if the instructor did anything differently.

13:43 -- Let's watch the instructor's approach.

13:45 -- It looks like the instructor did things a bit differently. I'll show you their code, and then explain the difference:
```
componentDidMount() {
fetch("https://api.imgflip.com/get_memes")
    .then(response => response.json())
    .then(response => {
        const {memes} = response.data
        console.log(memes[0])
        this.setState({ allMemeImgs: memes })
    })
```

13:48 -- It looks like the instructor just pulled the most relevant data out of the API by setting:
> const {memes} = response.data

and as a result when he initialized state he did so using only the array of memes, rather than also including some extraneous JSON data as I did.

While I'm sure I would have realized my error if I would have proceeded to the next step on my own, watching the instructor's approach saved me a lot of time having to debug things on my own.

13:52 -- Here's the next challenge I need to complete for the capstone project:

```
/**
* Create 2 input fields, one for the topText and one for the bottomText
* Remember that these will be "controlled forms", so make sure to add
* all the attributes you'll need for that to work
*/
```
Before I do that, however, I'm going to commit this journal to GitHub, and take a quick break to rest my eyes and stretch my body.
___
14:19 -- That break ended up being longer than expected. On the bright side, however, I got some walking in and my eyes are feeling refreshed.

14:20 -- Anyway, let's get to adding input fields for our forms!

14:24 -- The instructor said that after adding inputs the next challenge would be to add an onChange event handler and handleChange method. However, to be more efficient I'm going to also take care of these now.

14:30 -- Finished! Here's what I've got inside my render method:

```
<input type = "text" name = "topText" value = {this.state.topText} onChange={this.handleChange}/>

<input type = "text" name = "bottomText" value = {this.state.bottomText} onChange={this.handleChange} />
```
and here's the accompanying handleChange method:

```
handleChange (event) {
    const {name, value} = event.target
    this.setState({
        [name]: value
    })
  }
```
14:34 -- Let's commit to GitHub and then see Bob's approach and if he recommends doing anything different.

14:41 -- It looks like the only thing we did differently was that he included placeholders within his text fields while I forgot to do so.

While my version of the application was still functional in every manner, it's always good to include placeholders to guide our users on what input they should provide.

14:44 -- Wow, this came so fast. We're already onto the final challenge of the capstone! Here is it below:

```
/**
* Create a method that, when the "Gen" button is clicked, chooses one of the
* memes from our `allMemeImgs` array at random and makes it so that is the
* meme image that shows up in the bottom portion of our meme generator site (`.url`)
*/
```

14:46 -- After reading what this challenge is demanding, my immediate reaction is that I probably am going to need to use *Math.random()* along with *Math.floor()* in order to choose a random item from the array. I am not positive of course, but this seems like a reasonable place to start.

14:49 -- I'm going to go to the bathroom, and take a quick break to stretch before tackling this final challenge!
___

15:11 -- I'm back. Let's doooooo it!

15:14 -- Right away I figured out that to complete this challenge we were going to need to add an onSubmit event handler and an accompanying handleSubmit() method.

I've added both and used a console.log() to confirm that they are properly wired. 

15:15 -- I feel that at this point we need to solve an algorithm of sorts. I think that inside my submitHandle I should... 
1. >use Math.random, and multiply it by the number of items in our array from the API.
1. > Use Math.floor to round down (because JavaScript uses a zero-index system with arrays rather than starting at 1)
1. Set the state of randomImg to allMemeImgs[randomNumber] with the variable randomNumber being the result of the various Math functions we performed earlier.

I'm sure I'll have to adjust this plan as I begin to execute on it, but thus far it seems to make some degree of sense.

15:29 -- It looks like the number of meme images we're getting from the API is 100.

15:31 -- Here's the code I'm working on right now:

```
handleSubmit () {
console.log(Math.floor(Math.random()*this.state.allMemeImgs.length))
}
```

15:33 -- Next I think I'm going to save the result from the above code to a variable.

15:34 -- Success! That was easy.

15:39 -- Here's where I'm at now:
```
handleSubmit () {
const randomNumber = Math.floor(Math.random()*this.state.allMemeImgs.length)
console.log(this.state.allMemeImgs)
}
```

15:40 -- I'm a bit stuck. I haven't yet figured out how to use dot or bracket notation to access only the image urls (written as having the property of url in the array).

15:47 -- My code here merely logs null to the console:
```
handleSubmit () {
const randomNumber = Math.floor(Math.random()*this.state.allMemeImgs.length)
console.log(this.state.allMemeImgs["url"])
}
```

15:54 -- I'm so baffled beyond baffled right now lol.

15:58 -- I've tried changing the syntax, but I'm still stuck:
```
handleSubmit () {
const randomNumber = Math.floor(Math.random()*this.state.allMemeImgs.length)
console.log([this.state.allMemeImgs["url"]])
}
```

15:59 -- I'll have to figure things out later. My battery is about to die. Bummer, I thought I was going to be able to finish the entire capstone in one session of grinding! :p

___
**Total time spent coding today**: 

**Total time spent coding thus far in May 2019**: 

**Total lifetime hours of coding**: 


