# Monday June 10th, 2019 Daily Coding Journal

8:27 -- Here we go. I'm finally in one spot for a while, let's get to coding!

8:29 -- In today's first pomodoro session I'm going to work on the [Mini-Max Sum algorithm](https://www.hackerrank.com/challenges/mini-max-sum/problem) on HackerRank. My current points total on HackerRank is 81, which is good enough for a global rank of 713,171.

8:32 -- Let's define the problem. We're given an array of 5 numbers. From those 5 numbers, we need to define what's the minimum possible sum from adding 4 of the numbers, and what's the maximum possible sum for adding 4 of the numbers.

8:33 -- The first thing I immediately think of when solving this problem is that it's going to require us to first order the numbers in our array. We need to order the numbers in our array from smallest to largest (or largest to smallest.)

8:41 -- Here's where I'm at thus far:
```
function sortNumber (a, b) {
  return a - b
}

function miniMaxSum(arr) {
arr = arr.sort(sortNumber);
console.log(arr)
}

miniMaxSum([1, 5, 4, 4, 5, 2, 3])
```

8:50 -- I've made some progress:
```
function sortNumber (a, b) {
  return a - b
}
function miniMaxSum(arr) {
arr = arr.sort(sortNumber);
let minimumResult = 0;
let maximumResult = 0;
console.log(arr);
const minimumSum = () => {
  for (let i = 0; i < 4; i++) {
    minimumResult+= arr[i]
  }
  console.log(minimumResult)
}
minimumSum();
}
miniMaxSum([11, 15, 4, 14, 5, 12, 3]
```
Right now, however, I've got some pretty severe stomach pain. I'm going to take a break, let it subside a bit, and then I'll come back to this problem which I've already almost solved.
___
11:32 -- I'm back. Let's finish solving this algorithm.

11:43 -- Finished. I'll show you the solution, and then I'll walk you through everything:

```
function sortNumber (a, b) {
  return a - b
}
function miniMaxSum(arr) {
arr = arr.sort(sortNumber);
let minResult = 0;
let maxResult = 0;
const minimumSum = () => {
  for (let i = 0; i < 4; i++) {
    minResult+= arr[i]
  }
}
const maximumSum  = () => {
  for (let i = arr.length-1; i > arr.length -5; i--) {
    maxResult+= arr[i]
  }
}
minimumSum();
maximumSum();
console.log(minResult, maxResult)
}
```
Here's how it works...

**1.** We create a function that has a parameter *arr* that takes in an array.
```
function miniMaxSum (arr) {
}
```
**2.** We add a function *sortNumber* that we can pass as an argument to our sort() method in order to sort our array. We also set our array to equal the value of the sorted array in order to overwrite the value of our original array with that of the sorted array.
```
function sortNumber (a, b) {
  return a - b
}
function miniMaxSum(arr) {
arr = arr.sort(sortNumber);
```
**3.** We then initialize our variables minResult and maxResult to 0. We will later console.log these two variables as the solution to the algorithm.
```
function sortNumber (a, b) {
  return a - b
}
function miniMaxSum(arr) {
arr = arr.sort(sortNumber);
let minResult = 0;
let maxResult = 0;
```
**4.** The next thing we need to do is create local *minimumSum* and *maximumSum* functions that will utilize for loops to cycle through our array; summing the four smallest numbers and saving them to a variable (minResult), as well as saving the sum of the 4 largest numbers to a variable (maxResult).

Apart from just defining these functions, we also need to call them.
```
function sortNumber (a, b) {
  return a - b
}
function miniMaxSum(arr) {
arr = arr.sort(sortNumber);
let minResult = 0;
let maxResult = 0;
const minimumSum = () => {
  for (let i = 0; i < 4; i++) {
    minResult+= arr[i]
  }
}
const maximumSum  = () => {
  for (let i = arr.length-1; i > arr.length -5; i--) {
    maxResult+= arr[i]
  }
}
minimumSum();
maximumSum();
```
**5.** The final thing we need to do is console.log our two results; logging them in one statement to match the output expected by the algorithm.
```
function sortNumber (a, b) {
  return a - b
}

function miniMaxSum(arr) {
arr = arr.sort(sortNumber);
let minResult = 0;
let maxResult = 0;
const minimumSum = () => {
  for (let i = 0; i < 4; i++) {
    minResult+= arr[i]
  }
}
const maximumSum  = () => {
  for (let i = arr.length-1; i > arr.length -5; i--) {
    maxResult+= arr[i]
  }
}
minimumSum();
maximumSum();
console.log(minResult, maxResult)
}
```
Niceeee!

12:03 -- I'm going to commit everything to GitHub, and then take a quick break.
___
**Total time spent coding today**: 

**Total time spent coding thus far in June 2019**: 

**Total lifetime hours of coding**: 