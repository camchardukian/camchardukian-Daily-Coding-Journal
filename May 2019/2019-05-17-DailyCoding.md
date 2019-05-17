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

**Total time spent coding today**: N/A
___
**Total time spent coding thus far in May 2019**: N/A
___
**Total lifetime hours of coding**: N/A