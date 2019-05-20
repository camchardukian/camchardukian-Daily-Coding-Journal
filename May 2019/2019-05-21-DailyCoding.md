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

**Total time spent coding today**: N/A
___
**Total time spent coding thus far in May 2019**: N/A 
___
**Total lifetime hours of coding**: N/A