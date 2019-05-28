# Wednesday May 29th, 2019 Daily Coding Journal

1:13 -- It's the start of another day, and another daily coding journal entry! As you may recall, I spent yesterday building a meme generator using React. If you're looking for that project, you can [find it on GitHub here](https://github.com/camchardukian/ReactProjects/tree/master/meme-generator).

1:21 -- I just spent a couple minutes updating my README file for this project on GitHub. Now, let's finish watching the capstone video, and take notes on how Bob developed his application differently than I did.

1:25 -- While he structured his code a little differently, Bob and I used essentially the same logic in executing the final step in the capstone project.

1:27 -- One interesting thing to note I observed when playing with the code, however, is that if one puts the onSubmit event handler on the form element, we can prevent the default submit from occuring using:

> event.preventDefault()

If we put the same onSubmit event handler on our button, however, the above code snippet does not seem to work.

1:31 -- Now we're going to watch a video on ["Writing Modern React Apps"](https://scrimba.com/p/p7P5Hd/cvDkySN). The first time I'll watch this video all the way through. The second time through I'll stop and take notes throughout.

1:36 -- The video basically just talked about the fact that React is advancing very quickly due to the fact that it is constantly being worked on by Facebook developers and the open source community.

The video also provides some links for recommended reading.

1:42 -- It's official, I've finally finished the *Learn React for Free* course!
I'm going to take a quick break and then I might just still be motivated enough for another coding session!
___
1:50 -- Wow oh wow, it's been a long time since I did any FreeCodeCamp. Let's get back to it!

1:55 -- Here's a great quote I just pulled from the [FreeCodeCamp exercise I'm working on](https://learn.freecodecamp.org/front-end-libraries/react/use-react-to-render-nested-components):
> You break down your UI into its basic building blocks, and those pieces become the components. This helps to separate the code responsible for the UI from the code responsible for handling your application logic. It can greatly simplify the development and maintenance of complex projects.

2:10 -- I've spent the last 15 minutes or so reviewing some of the basics. For example, I just wrote the following code from scratch:
```

class MyComponent extends React.Component {

  render () {
    return (
    <div>
<h1>  My First React Component! </h1>
    </div>
    )
  }
}

ReactDOM.render(<MyComponent/>, document.getElementById("challenge-node"))
```
2:11 -- It has been good to review the basics. I was literally laughing out loud when I couldn't figure out why something wasn't rendering only to realize I forgot to include document.getElementById within my ReactDOM.render.

2:12 -- How nerdy is the previous comment? Hahahahaa. Anyway, it's pretty late now and my left wrist is feeling pretty sore from typing well over 3,000 words today and hundreds upon hundreds of lines of code. Catch you in the morning!
```


___
**Total time spent coding today**: 

**Total time spent coding thus far in May 2019**: 

**Total lifetime hours of coding**: 

