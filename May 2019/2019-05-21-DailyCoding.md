# Tuesday May 21st, 2019 Daily Coding Journal

0:56 -- It's officially Tuesday! Close to 1am... Let's dooooo it!

0:57 -- The following notes are from [this video](https://www.youtube.com/watch?v=AwyoVjVXnLk) on promises.

1:03 -- In order to make a new promise, you need to provide a path for that promise to be either resolved or rejected.

1:08 -- We can pass the argument/method/keyword (I'm not sure of the right terminology) new Error to our reject method. Example:
```
reject(newError("The API call was unsuccessful. Please try again."))
```

1:14 -- I just finished watching Part II on promises. 

1:15 -- Next I'm going to watch and take notes on Coding Train's two part series on [async and await in JavaScript](https://www.youtube.com/watch?v=XO77Fib9tSI).

1:20 -- If a function returns a promise, you can use the *await* keyword which has something to do with having some promise resolve (Clearly I do not yet understand the await keyword).

1:22 -- The *await* keyword is only usable within the context of an asynchronous function.

1:24 -- It seems there is a keyword called *async* that can be added before a function is declared and that will modify said function to be asynchronous.

1:35 -- It looks like combining the use of async and await we can write code that is easier to read than if we were to chain a bunch of .then() functions. 

Having been [introduced in ES8](https://hackernoon.com/es8-was-released-and-here-are-its-main-new-features-ee9c394adf66), await and async may not be supported in ALL versions of all browsers, but given that they've been out for two years already, it would be advisable to start getting comfortable with them if you aren't already.

1:40 -- It's pretty late now so I'm going to get to bed. In the morning I'll start learning about promise.all in [this video](https://www.youtube.com/watch?v=01RTj1MWec0). I'll probably also start to watch Dylan Israel's videos on Scrimba about async and await. See you then!
___
5:16 -- Just slept for about 3 or 3.5 hours. Let's get in 20+ minutes of coding and then I'll allow myself to sleep some more.

5:21 -- It seems that Promise.all() needs an array passed to it. With that array, we can then chain a .then() method and a .catch() method. The .then() method will work by waiting for our all of our original promises to be resolved.

Then, it will return the results of all of those promises in an array which maintains the order in which the original promises were made. Of course, if there any unexpected problems that occur during this process, the .catch() method will then come into play.

5:30 -- To reiterate, promise.all() has a weakness in that if *ANY* of the individual promises it contains are rejected, then the entire array would then be rejected.

5:32 -- I've now finished *The Coding Train's* entire series on promises, async, await, and promise.all(). Now I'm going to go look over Dylan Israel's videos on async and await.

5:42 -- I've just finished watching the [first video](https://scrimba.com/p/p4Mrt9/cKLyeuy) Dylan has on async and await. Now let's get into the [second video](https://scrimba.com/p/p4Mrt9/c2vQ4Cg) (which is a challenge video).

5:43 -- Dylan's challenge for us is to convert the following function into a function that utilizes the await and async keywords:

```
function resolveAfter3Seconds() {
  return new Promise(resolve => {
    setTimeout(() => {
      resolve('resolved');
    }, 3000);
  });
}

```

5:46 -- I'm guessing that this is roughly what he wanted me to create, but I'm not yet sure on the details...
```
async function cameronsResolveAfter3Seconds () {

}
```

5:53 -- While I'm not sure on the specifics, here's kind of my rough idea on using async and await:

```
async function cameronsResolveAfter3Seconds () {
const simulatedApiResponse = setTimeout(() => {
    console.log("resolved");
}, 3000); //closing parenthesis for setTimeout
const jsonify = await simulatedApiResponse + "IN THIS STEP WE WOULD NORMALLY USE JSON ON OUR PROMISE THAT HAD JUST BEEN RESOLVED"
console.log(jsonify)
}

cameronsResolveAfter3Seconds ()
```

5:56 -- It seems like I was on the right track. Dylan's solution was pretty similar to mine, apart from the fact that he didn't do anything with json this time.

```
async function getAsyncData() {
    const result = await resolveAfter3Seconds();
    console.log(result);
}

getAsyncData();
```

5:58 -- I'm going to brush my teeth, and then sleep a bit more. When I wake up I'll do another few videos on promises and then continue on with the Learn React for Free course -- probably in the afternoon.
___
7:05 -- Whoa. For whatever reason I haven't gone to sleep yet. I've already gone through my morning routine and gotten about 2 hours of productive work in today despite going to sleep at 2am last night lol. Let's stay on the grind!

7:11 -- Promises are great for taking a task that takes a long time to complete, and move the processing of that task into the background instead of halting your entire application until that task is completed.

7:18 -- [The video I'm watching right now](https://www.youtube.com/watch?v=DHvZLI7Db8E) is super noob friendly. If you're a beginner developer that has somehow stumbled upon my journal, I definitely recommend watching Web Dev Simplified's video on promises.

7:20 -- A neat thing I learned in Web Dev Simplified's promise video is the **promise.race()** method. Similar to promise.all(), promise.race() accepts an array of promises as its argument.

The key difference is that promise.race() does not force you to wait for all of the promises to be resolved before returning something.

In fact, promise.race() does not even return all of your promises! Promise.race() will return only the first promise that is resolved.

7:26 -- I feel like I'm really starting to get promises. I'm going to watch another two videos on promises and then I'll continue the React course on Scrimba.

7:27 -- [Let's watch Techsith's tutorial on promises](https://www.youtube.com/watch?v=s6SH72uAn3Q).

7:36 -- While most of Techsith's tutorial was a review to me at this point, I did get one gold nugget on a possible use case for promise.race().

If we trying to fetch data from a server or API, we will often try to fetch said data from multiple sources for redundancy purposes.

This allows us to still get the data we need even if one of our potential data sources is not functioning properly. By using promise.race() we can fetch data from multiple sources and just return data from the first successful API call or whatnot.

7:41 -- I feel I'm about ready to get back into the Scrimba *Learn React for Free* course. In the next pomodoro session I'll take notes on [Traversy Media's async JS crash course](https://www.youtube.com/watch?v=PoRJizFvM7s) that talks about callbacks, promises, and asnyc wait. That'll be the last video before I at least attempt to get back on Scrimba.
___
10:12 -- On to the next pomodoro session. Let's get through Traversy Media's async JS crash course!

10:27 -- If your promise is rejected but you forget to include a .caught() method you'll receive an error of *uncaught (in promise) error*.

10:28 -- Brad says that more and more JavaScript libraries are starting to implement promises. With that being said, he said that usually as a developer you'll spend more time dealing with the responses of promises than creating them yourself. But... that you definitely *should* know how to create them yourself.

10:37 -- I finished Brad's video. I'm going to take a quick break to stretch and clean my room a bit. Then we'll finally get back to the Scrimba React course!

10:52 -- I'm back. Let's get to it!

10:56 -- Fetch is a global function. My interpretation of this is that fetch can be called from anywhere within our program because fetch isn't limited to a single local scope (in which it couldn't be called outside of).

11:04 -- I just finished watching the [*Fetching data from an API*](https://scrimba.com/p/p7P5Hd/c79Jask) video again.

11:05 -- Now I'm going to write the code from the video by hand a few times to internalize the syntax and logic patterns. Then, later today I'll try to rebuild everything from scratch.

11:19 -- I finished writing the code by hand twice thus far. My neck is starting to get a little stiff. I'm going to take a break for lunch, edit a video or two, maybe take a nap and then get back to it this afternoon.
___
15:12 -- Where have the last four hours gone? lol. Between eating a couple lunches, taking an hour long nap, and going for a walk, a ton of time had passed!

15:13 -- Let's spend another 15 minutes or so writing code by hand and then I'll try to implement API calls by myself.

15:29 -- I just wrote the code by hand 3 times and played around with giving some of the argument throughout the promise different names. I noticed something strange.

```
componentDidMount() {
        this.setState({loading: true})
        fetch("https://swapi.co/api/people/1")
            .then(response => response.json())
            .then(data => {
                this.setState({
                    loading: false,
                    character: data
                })
            })
```

In the above code blog I can change the name of response to *"q"* or whatever I'd like the argument to be named and my app remains functional. If, however, I change the name of data my app is in a perpetual state of loading.

15:32 -- DUH. I just realized that it isn't so strange after all. The reality is that both response and data were arbitrarily named.

The reason I couldn't change the name of data without my application breaking, however, is because I forgot to adjust setting my state on character from data to the new variable name.

The new code down below works just fine.

```
componentDidMount() {
        this.setState({loading: true})
        fetch("https://swapi.co/api/people/1")
            .then(bananaPeel => bananaPeel.json())
            .then(arbitraryName => {
                this.setState({
                    loading: false,
                    character: arbitraryName
                })
            })
    }
```

15:35 -- Would naming my arguments in the manner I have done be advisable? Of course not.

We should follow coding conventions whenever possible to make our code easier to read for both others and our future selves.

With that being said, I do believe there is a lot of value in playing with code and testing to see what elements of our code our keywords versus variable/function/argument names that were arbitrarily chosen.

This gives us a deeper understanding of the code we are working with and makes us better software engineers.

15:37 -- My neck is sore. I'm going to take a quick 5-10 minute break, write the code from scratch one more time, and then attempt to re-engineer the solution on Scrimba from scratch.

___

15:46 -- Let's get back to work.

15:51 -- I've finished writing the code from scratch for the last time. Now, let's build the solution from scratch.

15:57 -- I read over some of the documentation from the (and copy/pasted it onto Scrimba). I'm starting from eventually a blank canvas to solve this problem. Below is all the information I am giving myself access to in order to solve this problem:

```
// Note to self: Use this URL to get information about planet 3. https://swapi.co/api/planets/3/

// Information from swapi documentation: A Planet resource is a large mass, planet or planetoid in the Star Wars Universe, at the time of 0 ABY.

// Example response: {
//     "climate": "Arid",
//     "created": "2014-12-09T13:50:49.641000Z",
//     "diameter": "10465",
//     "edited": "2014-12-15T13:48:16.167217Z",
//     "films": [
//         "https://swapi.co/api/films/1/",
//         ...
//     ],
//     "gravity": "1",
//     "name": "Tatooine",
//     "orbital_period": "304",
//     "population": "120000",
//     "residents": [
//         "https://swapi.co/api/people/1/",
//         ...
//     ],
//     "rotation_period": "23",
//     "surface_water": "1",
//     "terrain": "Dessert",
//     "url": "https://swapi.co/api/planets/1/"
// }
```
16:01 -- So far it's smooth sailing. To be fair, I haven't got to the most challenging part of the problem, but I'm off to a good start with everything properly rending and functioning without errors thus far:

```
import React from "react"

class App extends React.Component {
    constructor () {
        super()
        this.state = {
            isLoading: false,
            name: {}
        }
    }
    
    componentDidMount() {
        
    }
    
    render() {
        return (
            <p> This is some test text to display for my sanity... </p>
        )
    }
}

export default App
```

16:04 -- Right as I was starting to get confident I feel as if I've hit a brick wall. I feel like I have literally no idea what to do now lol. I know about fetch, and .json, and chaining the .then() methods, and setting my state, but I forgot how I'm supposed to start things off inside componentDidMount.

16:05 -- Actually... I think I do remember. The first thing I need to do is set my state of isLoading to be true. This will prep my application to render *loading...* to the screen while the user waits for the data to be successfully retrieved from the API.

16:11 -- I'm continuing to make progress. My application now sets the state of isLoading to true and displays a loading message.
```
import React from "react"

class App extends React.Component {
    constructor () {
        super()
        this.state = {
            isLoading: false,
            name: {}
        }
    }
    
    componentDidMount() {
        this.setState({isLoading: true})
    }
    
    render() {
         const text = this.state.isLoading ? "loading...." : "We'll add some API stuff here later"
        return (
            <div>
            <p> {text} </p>
            </div>
        )
    }
}

export default App
```

16:13 -- Now I just have to successfuly fetch from the API, run .json on the response, and use the returned data to setState of name (of the planet) to equal data, and setState of isLoading to false (because if we've gotten to this point the API call was obviously successful.)

16:16 -- Well, this is a bizarre error. The URL of the API I'm trying to access is (https://swapi.co/api/planets/3/). But, I can't seem to use this data inside of the fetch() method because the two forward slashes comment out the rest of the URL.

I then tried to add a back slash to escape the forward slashes but that seems to have just made my url unreadable lol.

Surely I can't be the only person to have had this problem.

16:19 -- I guess I'll just try accessing the API using this URL (swapi.co/api/planets/3/). Later I'll read up about if accessing it in this way poses any security risks.

16:21 -- It seems like I'm not using the fetch() method correctly. I will NOT cheat and watch the tutorial to figure out the solution.

But, there's no sense in me just randomly throwing things against the wall either when I'm facing more of a syntax issue rather than a logical error.

For that reason, I'm going to quickly consult the MDN for information on using fetch. If MDN's explanation is too complex for me to understand I'll watch some youtube tutorials on fetch (that are not directly related to the problem I'm currently trying to solve).

16:25 -- On an unrelated note, I just realized that Markdown doesn't have a native underlining feature. If I want to underline I have to do so with CSS. This seems a bit crazy to me!

16:30 -- Well, I found at least one problem with my code from earlier. I forgot to wrap the URL I passed to my fetch() method in quotes!

16:31 -- It seems adding the double quotes solved not only the *expression expected* error I was encountering earlier, but also the error in which the double slashes were resulting in the rest of my URL being commented out.
#MakingProgress
Yeah baby!

16:35 -- I'm soooo close. Check out my code:

```
componentDidMount() {
        this.setState({isLoading: true})
        fetch("https://swapi.co/api/planets/3/")
        .then( (response) => {
            return response.json
        }).then(data => {
            console.log(data.name)
        }) 
    } 
```

16:36 -- For some reason, however, whether I console.log() data, or data.name, I simply receive the json method or a string with the text "json".

16:37 -- Unfortunately, my wrists are starting to get a bit sore now so I'm going to have to take a break. Catch you again later!
___
17:24 -- It seems the grind never stops today. Be a machine! 

17:25 -- I'm going to work through and take notes on a Traversy Media video on the fetch() method. The video is called [Fetch API Introduction](https://www.youtube.com/watch?v=Oive66jrwBs) if you'd like to follow along with me.

17:31 -- The fetch method takes in a file name or URL as its argument.

17:32 -- Fetch always returns a promise.

17:33 -- Remember to NOT put a semi colon after your fetch() method (because doing so would end the statement and prevent you from being able to chain .then() )

17:38 -- I found one of the mistakes I was making earlier. Instead of writing:
> return response.json()

I simply wrote:
>return response.json

Unfortunately, the latter does not work as I intended because I am not actually calling the .json() method on my response.

17:46 -- I'm getting closer, but it seems I'm still missing something. I'm repeatedly getting an error that:

*Invariant Violation: Objects are not valid as a React child (found: object with keys {}). If you meant to render a collection of children, use an array instead.*

I've written the code that produces said error below:

```
import React from "react"

class App extends React.Component {
    constructor () {
        super()
        this.state = {
            isLoading: false,
            name: {}
        }
    }
    
    componentDidMount() {
        this.setState({isLoading: true})
        fetch("https://swapi.co/api/planets/3/")
        .then( (response) =>
         {
        return response.json()
        })
        .then( (data) => {
          this.setState({
        isLoading: false,
        name: data.name
            })
        }
        )
    }
    
    render() {
         const text = this.state.isLoading ? "loading...." : this.state.name
        return (
            <div>
            <p> {text} </p>
            </div>
        )
    }
}
export default App
```

17:55 -- I've now written a workable solution. Here's where I'm at now:
```
import React from "react"

class App extends React.Component {
    constructor () {
        super()
        this.state = {
            isLoading: false,
            name: "" // could also use square brackets, just curly brackets seem to cause issues.
        }
    }
    
    componentDidMount() {
        this.setState({isLoading: true})
        fetch("https://swapi.co/api/planets/3/")
        .then( (response) =>
         {
        return response.json()
        })
        .then( (data) => {
            this.setState({
                isLoading: false,
                name: data.name
            })
        }
        )
    }
    
    render() {
         const text = this.state.isLoading ? "loading...." : this.state.name
        return (
            <div>
            <p> {text} </p>
            </div>
        )
    }
}

export default App
```

17:57 -- It appears the thing I was having problems with earlier was my ternary operator. I think I was getting an error message because my isLoading state was initially set to equal curly brackets.

I used a ternary operator with different logic (that relied on this.state.name rather than this.state.isLoading), amongst countless other hacks.

No matter what I tried, however, it seemed the only thing that mattered was that I NOT initalize my state with curly brackets. I should instead use square brackets or an empty string.

18:03 -- Anyway, I'm proud to have solved this problem! I'm going to go walk, maybe eat dinner, and possibly meet a friend later tonight.

Catch ya later!
___
Continue with Brad's fetch API video upon my return...

___

**Total time spent coding today**: N/A
___
**Total time spent coding thus far in May 2019**: N/A 
___
**Total lifetime hours of coding**: N/A