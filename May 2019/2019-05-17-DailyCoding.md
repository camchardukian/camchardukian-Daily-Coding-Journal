# Friday May 17th, 2019 Daily Coding Journal

9:33 -- I went to MiniStop (a popular convenience store in Vietnam) to get out of the house and get some work done. I ended up gettting "ambushed" by this 59 year old Vietnamese woman who didn't speak any English but was speaking in Vietnamese to me about my life, her son, and being retired lol. Really friendly of her to just randomly talk to me, and it goes to show again that there's almost never any reason to feel anxiety about starting a conversation with strangers. Anyway, let's get started talking about conditional rendering.

9:36 -- Bob Ziroll says in [this video](https://scrimba.com/p/p7P5Hd/c4kJNSL) that one of the challenging things about teaching (and presumably learning) React is that there are a variety of tools that can be used in a number of ways and that we as developers aren't constrained to just one way of using a tool.

This along with the fact that much of React is written with just plain JavaScript can make it difficult for an instructor to determine which method or way of doing things they should teach students.

9:51 -- I just finished watching the conditional rendering video all the way through. It was dense, but not completely over my head. Plus, I'm sure I'll be a lot more confident about things after taking notes on the video. Let's take some notes!

9:54 -- When we make a call to an API, often the data we're getting is not immediately returned. We may have to wait a second or more
to receive the data. Of course, if our webpage appears to be unresponsive during that time users may think our site simply crashed. To avoid this, we may want to display some kind of loading screen or loading message.

9:58 -- It's very common for our application to have a state property of isLoading that's set to either true or false:
```javascript
 this.state = {
            isLoading: true
        }
```
If true, the loading message or whatnot will be displayed. If false, the loading message will cease to display and the application will simply render the content (often the data from an API for example).

10:04 -- One (or THE, I'm not quite sure yet), lifecycle method we'll usually use during the process of conditional rendering is **componentDidMount()**

10:08 -- Bob started talking about the **setTimeout** JavaScript method. While the name seems pretty self-explanatory, I'm going to watch another video about this method to make sure I understand everything clearly before continuing.

10:09 -- I'm now watching [this video](https://www.youtube.com/watch?v=kOcFZV3c75I) from FreeCodeCamp. According to Beau Carnes, the window object has two different timing events that allow the execution of code at specific time intervals. These two methods are **setTimeout()** and **setInterval()**.

10:18 -- My neck is starting to feel a little cramped. I'm going to take a quick walk, maybe get a little something to eat and then I'll take notes on **setTimeout()** and **setInterval()**.
___
11:06 -- Just finished a 10-15 minute walk and lunch. Let's get to those notes.

11:07 -- For the setTimeout() method we pass a function and numbers of milliseconds. After the specified number of milliseconds have passed, the function will then run.

11:11 -- Here's an example code block for the setTimeout() method.
```javascript
setTimeout(ninjaKick, 4000)

console.log("Quick! The ninja is coming! Close this window before he gets you!")

function ninjaKick () {
    console.log("Too slow... The ninja has kicked you in the face.")
}
```

11:15 -- If you look at the code I've written above, here's what will happen. First, the plain console.log will run. The user will get a message that,
> "Quick! The ninja is coming! Close this window before he gets you!"

Assuming the window or application remains open, however, four seconds later (four seconds because we passed 4000 milliseconds as an argument to setTimeout) the user will then get the message, 
>  "Too slow... The ninja has kicked you in the face."

11:21 -- According to Beau, it is possible to stop the function from running even after the setTimeout() method has been called. *How?* Let me keep watching to find out for you.

11:23 -- Fortunately the process for stopping the function passed to the setTimeout() method is pretty simple. Here's a list of things we need to do...

1. Assign our setTimeout() method to a variable.
1. Call the **clearTimeout() method with our variable from step 1 passed in as the argument.

Hmm... let's show you some code to help you (and I) internalize this. Continuing with the above example...
```javascript
const clearedVariable = setTimeout(ninjaKick, 4000);

console.log("Quick! The ninja is coming! Close this window before he gets you!");

clearTimeout(clearedVariable);

function ninjaKick () {
    console.log("Too slow... The ninja has kicked you in the face.");
}
```
In the above example, the following text would be logged to the console: 
> "Quick! The ninja is coming! Close this window before he gets you!"

However, the ninjaKick function would never actually run because it was assigned to the clearedVariable that was passed to the clearTimeout method. Thus, only the vanilla console.log() warning users about the incoming ninja would ever actually log to the console.

11:38 -- Wow! I can't believe we spent 30 minutes talking just about the setTimeout() method. With that being said, I'm going to take a break now, and discuss the setInterval() method in the next pomodoro session!
___
19:52 -- I'm feeling a bit tired. I think I may have just had some bad fried seaweed + mixed seafood rice. Nonetheless, we shall persevere lol. Here I come setInterval()!

19:53 -- The setInterval() method is similar to setTimeout() in that you the developer will pass in a function and time inverval in milliseconds. The main difference, however, is that the setInterval() will call your function continuously (waiting your passed number of milliseconds between each function call).

20:03 -- I really like the example Beau gave in [this video](https://www.youtube.com/watch?v=kOcFZV3c75I) so I find it unnecessary to create my own from scratch. Let me just give you Beau's code (I refactored it slightly for modern ES6 syntax and to simplify things a bit for JavaScript noobs) and walk you through it:
```javascript
let count = 0;
setInterval(counter, 1000);
function counter() {
    console.log(++count)
}
```
1. We initialize our count variable to 0.
1. We create a function called **counter()** which will increment our count variable and log it to the console.
1. We call setInterval with *counter* and *1000* (milliseconds) passed as arguments.
1. We see 1 logged to the console, followed by 2 a second later, followed by 3, and so on.

20:15 -- Hopefully you found the above explanation useful. Oh, and here's another thing to note. We can use the clearInterval() method (with a variable passed to it) if we ever want our function to stop running (just like the clearTimeout method).

20:17 -- Now that we've got setTimeout and setInterval() down pretty solid, let's get back to the conditional rendering video.

20:18 -- [The video](https://scrimba.com/p/p7P5Hd/c4kJNSL) and concepts presented within it feel a lot more managable to understand this time around (thus far).

One thing we should note is that the componentDidMount() lifecycle method is used to give us a chance to run some code after a component mounts to the screen for the first time.

By mount, I assume the course instructor means is successfully rendered or processed, though I cannot yet confirm that 100%.

20:24 -- Generally speaking, remember that whenever a component receives a different prop (or the same prop with a different value), the render method that encloses said component will run again.

20:28 -- This has been a solid session. Let's take a break.
___
22:49 -- Today has been a decent day of programming. Unfortunately, I had to spend most of my evening focusing on something else important so I'm not going to be able to get in another programming session. We'll hit it hard again tomorrow though!


___
**Total time spent coding today**: 2 hours 14 minutes
___
**Total time spent coding thus far in May 2019**: 35 hours 37 minutes
___
**Total lifetime hours of coding**: 531 hours 33 minutes