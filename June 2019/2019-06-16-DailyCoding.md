# Sunday June 16th, 2019 Daily Coding Journal

6:41 -- I feel like I'm finally starting to get back into some kind of rhythm. Let's get off to an early start today and produce.

6:44 -- I currently have 106 points on HackerRank which is good for a global rank of 600,012.

6:46 -- I'm working on the [Breaking the Records algorithm on HackerRank](https://www.hackerrank.com/challenges/breaking-best-and-worst-records/problem).

6:47 -- Let's define the problem. There's a basketball player named Maria. She wants to count how many times in a season she breaks her record for most points and least points.

The points she scores in her first game establishes the baseline through which we'll make our comparisons to evaluate whether she broke a record or not.

We have a function *breakingRecords* that has a parameter *scores* that takes in an array of numbers as its argument.

Our goal is to use this function to return two numbers separated by a space that respectively represent the number of times she broke her record for highest points and lowest points in a game throughout her season.

6:56 -- It's a start:
```
function breakingRecords(scores) {

}
```

6:59 -- Moving forward...
```
function breakingRecords(scores) {
  let result = [0, 0];
for (let i = 0; i < scores.length; i++) {
}
}
```
7:11 -- Almost finished:
```
function breakingRecords(scores) {
  let maxMinRecord = [0, 0];
  let maximum = scores[0];
  let minimum = scores[0];
for (let i = 0; i < scores.length; i++) {
  if (scores[i] > maximum) {
    console.log(`${scores[i]} is greater than ${maximum}`)
        maximum = scores[i]
        maxMinRecord[0]+=1
  }
  else if (scores[i] < minimum) {
    console.log(`${scores[i]} is less than ${minimum}`)
    minimum = scores[i]
    maxMinRecord[1]+=1
  }
}
  console.log(maxMinRecord)
}
```
Just need to clean things up a little and console.log() my maxMinRecord array in the correct format.

7:17 -- Finished! Here's my final solution:
```
function breakingRecords(scores) {
  let maxMinRecord = [0, 0];
  let maximum = scores[0];
  let minimum = scores[0];
for (let i = 0; i < scores.length; i++) {
  if (scores[i] > maximum) {
        maximum = scores[i]
        maxMinRecord[0]+=1
  }
  else if (scores[i] < minimum) {
    minimum = scores[i]
    maxMinRecord[1]+=1
  }
}
return (maxMinRecord.join(" "))
}
breakingRecords([10, 5, 20, 20, 4, 5, 2, 25, 1])
```
7:18 -- I'm going to take a break to stretch and have breakfast. Then, I'll explain everything.
___
7:41 -- Just finished commiting this journal entry to GitHub, stretching, and making a green smoothie for breakfast.

Now, let's talk about how I approached this problem.

7:42 -- The first thing I did was create a function *breakingRecords* that has a parameter *scores* which takes in an array of numbers as its argument.
```
function breakingRecords(scores) {

}
```

7:44 -- Next, we need to define several variables. *maxMinRecord* will be an array whose first value represents how many times Maria broke her record for highest points in a game, and the second value represents how many times she broke her record for lowest points in a game.

Our *maximum* and *minimum* variables are intialized to the first value in the array passed in as an argument to our breakingRecords function.

The reason we use the first value in the array to initialize our variables is because Maria's first game of the reason operates as the baseline through which all further comparisons are made.
```
function breakingRecords(scores) {
  let maxMinRecord = [0, 0];
  let maximum = scores[0];
  let minimum = scores[0];
}
```
7:49 -- Next, we write a for loop that'll cycle through all the values in our *scores* array. Nested in our scores array is an *if statement* with logic that basically states, if Maria's points in her current game is greater than her previous maximum, we'll update her record to the current game's number of points and increment Maria's number of times she has broken her maximum scoring record.

We use similar logic to state that if in Maria's current game she has scored less than her minimum number of points for a single game this season, we'll update her minimum (obviously decreasing it in the process), and increment the number of times she's broken her minimum record by one.
```
function breakingRecords(scores) {
  let maxMinRecord = [0, 0];
  let maximum = scores[0];
  let minimum = scores[0];
for (let i = 0; i < scores.length; i++) {
  if (scores[i] > maximum) {
        maximum = scores[i]
        maxMinRecord[0]+=1
  }
  else if (scores[i] < minimum) {
    minimum = scores[i]
    maxMinRecord[1]+=1
  }
}
}
```
7:56 -- The only thing left to do now is join our maxMinRecord array, separating our two values by a space in the process, and then return *maxMinRecord* as our solution to the algorithm!
```
function breakingRecords(scores) {
  let maxMinRecord = [0, 0];
  let maximum = scores[0];
  let minimum = scores[0];
for (let i = 0; i < scores.length; i++) {
  if (scores[i] > maximum) {
        maximum = scores[i]
        maxMinRecord[0]+=1
  }
  else if (scores[i] < minimum) {
    minimum = scores[i]
    maxMinRecord[1]+=1
  }
}
return (maxMinRecord.join(" "))
}
```
7:58 -- I hope my explanation of this problem has helped you understand it!

8:05 -- Just commited that solution to my HackerRank algorithm repo.

8:06 -- I now have 116 points on HackerRank which is good enough for a global rank of 565,243.

8:07 -- In the next pomodoro session, I'll solve the [Divisible Sum Pairs algorithm on HackerRank](https://www.hackerrank.com/challenges/divisible-sum-pairs/problem).
___
10:01 -- I'm back. I'm going to try to do a quick pomodoro session before heading out to see some family that's leaving for the airport later.

10:04 -- This problem is a little bit complicated to wrap one's head around. It seems... actually, I can't explain things off the top of my head.

I'm going to have to play around with this function and spend some more time reading to fully understand what is happening.

10:11 -- Writing the following code has helped me visually understand the variables that we are working with:
```
function divisibleSumPairs(n, k, ar) {
console.log(`n = ${n} and is the integer length of the array "ar"`)

console.log(`k = ${k} and is the integer we are performing division with`)

console.log(`ar = ${ar} and is our array of integers`)
}

divisibleSumPairs(3, 12, [2, 3, 5, 1, 5])
```
10:14 -- I'm starting to understand the problem now. We need to see which combinations of two integers are divisible by *k* (or technically speaking, the value we pass to k).

10:15 -- I think we can do this by looping through our array, adding up every possible pair of numbers, and in the process increment a counter variable whenever we find a pair of two numbers in the array that are divisible by *k*.

10:17 -- Unfortunately, it's time to go so I'll have to work on the implementation later. See you then!

___
**Total time spent coding today**: 

**Total time spent coding thus far in June 2019**: 

**Total lifetime hours of coding**: 