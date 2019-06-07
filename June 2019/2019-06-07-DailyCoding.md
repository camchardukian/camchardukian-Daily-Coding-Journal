# Thursday June 6th, 2019 Daily Coding Journal

12:36 -- I spent an hour walking across the city this morning. It's always good to get exercise.

On the not so positive side, I'm running on about 5.5 hours of sleep.

But, back to being optimistic. The reason I got to sleep so late last night was because I spent 2+ hours recording another tutorial for the daily developer show :D

12:40 -- Let's get to coding.

12:43 -- I'm now working on the [Plus Minus](https://www.hackerrank.com/challenges/plus-minus/problem) algorithm on hackerrank.

12:44 -- Let's define the problem. It seems we're getting an array of numbers:
>[1, 2, 0, -5, 0]

From that array of numbers we need to figure out how many of those numbers are positive numbers, how many are negative numbers, and how many are 0. In this example, we'd get:
> 2 positive numbers, 1 negative number, 2 zeros.

From there, we need to divide each value (2, 2, and 1 in this example), by the length of the array.
> 2 / 5 = 0.4; 1 / 5 = 0.2 ; 2 / 5 = 0.4

Then we need to print the results from our division operation all on seperate lines.

0.4

0.2

0.4

While the numbers came out nicely in this example, in some situations it may also be important for us to round each of our outputs to the 6th decimal place (per the demand of the problem creator).

We could probably multiply by some large numbers like 1000000, use Math.round(), and then divide by 1000000 to complete this part of the problem.

12:59 -- I started out by writing out a function that takes in an array, and initalizing a count variable to an object that has keys for *positiveCount*, *negativeCount*,and *zeroCount*:

```
function plusMinus(arr) {
let counter = {
  positiveCount: 0,
  negativeCount: 0,
  zeroCount: 0
}
}
plusMinus([1, 2, -9, 0, 3])
```
13:01 -- The next thing we need to do is count how many of each value there are (how many postives, negatives, and zeros).

13:09 -- I just added a loop in that'll calculate and help us count how many positive, negative, and zero numbers there are:
```
function plusMinus(arr) {
let counter = {
  positiveCount: 0,
  negativeCount: 0,
  zeroCount: 0
}

for (let i = 0; i < arr.length; i++) {
  if (arr[i] > 0) {
    counter.positiveCount++
  }
  else if (arr[i] < 0) {
    counter.negativeCount ++
  }
  else {
    counter.zeroCount++
  }
}
}
plusMinus([1, 2, -9, 0, 3])
```
13:10 -- Now I'm feeling a bit tired. I'm going to have to take a break.

13:33 -- I took power nap at the coffee shop, but I'm feeling like it's quite enough to get me up and going again. I need to change my environment. I'm going to go for a walk, and maybe grab lunch to get my energy back again.
___

14:17 -- Tried to go to an old bun bo (beef soup) place I liked eating at, but apparently it closed and moved to the outskirts of the city.

Oh well, I got this huge korean lunch. I just ordered curry rice, but after their complimentary soup, side of kimchi (which I didn't eat), eggs, and vegetables I felt full even before I started the main dish hahaha. 

Anyway, back to the problem.

14:30 -- I used a for in loop to divide the value of each key by the length of our array. Then, I pushed the resulting value into a results loop.
```
function plusMinus(arr) {
let counter = {
  positiveCount: 0,
  negativeCount: 0,
  zeroCount: 0
};
let results = [];

for (let i = 0; i < arr.length; i++) {
  if (arr[i] > 0) {
    counter.positiveCount++
  }
  else if (arr[i] < 0) {
    counter.negativeCount ++
  }
  else {
    counter.zeroCount++
  }
}
for (let key in counter) {
  results.push(counter[key] / arr.length)
}
console.log(results)
}

plusMinus([1, 2, -9, 0, 3])
```
14:31 -- It looks like there are still two more things I have to do. The first is that I need to be sure to loop through my results array and round each value to the 6th decimal place. Then, I have to print each value to the console on its own line.

14:36 -- I updated my for in loop to ensure that it would round each result to the 6th decimal place:
```
for (let key in counter) {
  results.push(Math.round(counter[key] / arr.length*1000000)/1000000)
}
```
14:42 -- I tried using the following code:
> console.log(results.join("").replace(",", \<br/>))

But then I remembered that I'm operating inside of JavaScript and not JSX. Hmmm... I'll try again using document.write.

14:45 -- Unfortunately, it seems document.write doesn't work in repl.it. I got an error that:
> ReferenceError: document is not defined

14:49 -- While it's not the most elegant solution I ended up solving the problem by just writing console.log() three times. Here's my final solution:
```
function plusMinus(arr) {
    let counter = {
        positiveCount: 0,
        negativeCount: 0,
        zeroCount: 0
    };
    let results = [];

    for (let i = 0; i < arr.length; i++) {
        if (arr[i] > 0) {
            counter.positiveCount++
        }
        else if (arr[i] < 0) {
            counter.negativeCount++
        }
        else {
            counter.zeroCount++
        }
    }
    for (let key in counter) {
        results.push(Math.round(counter[key] / arr.length * 1000000) / 1000000)
    }
    console.log(results[0])
    console.log(results[1])
    console.log(results[2])
}
```

14:56 -- It's been a good run. I'm going to commit this to GitHub and then maybe get some exercise or sleep. See you later!

___
**Total time spent coding today**: 

**Total time spent coding  thus far in June 2019**: 

**Total lifetime hours of coding**: 