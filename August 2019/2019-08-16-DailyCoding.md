# Friday August 16th, 2019 Daily Coding Journal

11:32 -- Here we go. Let's continue the coding momentum.

11:34 -- We're going to start today by working on the [Between Two Sets](https://www.hackerrank.com/challenges/between-two-sets/problem) algorithm on HackerRank.

11:36 -- It looks like this algorithm is giving us two arrays. Our job is to find all the numbers that satisfy the following two conditions:

1. The elements of the first array are all factors of the integer being considered.

1. The integer being considered is a factor of all elements of the second array.

The numbers that satisfy the two above conditions are referred to as numbers that are "between the two arrays".

11:39 -- As usual, I'm going to attempt to solve this problem on my own first. Later on I'll explain how I came to my solution.

11:48 -- Not sure if I'm on the right track, but here's what I have thus far:
```
function getTotalX(a, b) {
let initialList = [];
for (let i = a[a.length-1]; i < b[0]; i+=a[a.length-1]) {
  initialList.push(i)
}
console.log(initialList)
}
```
12:00 -- I feel like I've gotten through the first half of the problem:
```
function getTotalX(a, b) {
let initialList = [];
let semiFilteredList = [];
let counter;
for (let i = a[a.length-1]; i < b[0]; i+=a[a.length-1]) {
  initialList.push(i)
}
for (let i = 0; i < initialList.length; i++) {
  semiFilteredList.push(initialList[i])
  counter = 0;
  for (let ii = 0; ii < a.length; ii++) {
    if (initialList[i] % a[ii] !== 0) {
      counter+=1
    } 
  }
  if (counter > 0) {
    semiFilteredList.pop()
  }
 }
console.log(semiFilteredList)
}
```
12:11 -- Here's my current solution:
```
function getTotalX(a, b) {
let initialList = [];
let semiFilteredList = [];
let finalList = [];
let counter;
for (let i = a[a.length-1]; i < b[0]; i+=a[a.length-1]) {
  initialList.push(i)
}
for (let i = 0; i < initialList.length; i++) {
  semiFilteredList.push(initialList[i])
  counter = 0;
  for (let ii = 0; ii < a.length; ii++) {
    if (initialList[i] % a[ii] !== 0) {
      counter+=1
    } 
  }
  if (counter > 0) {
    semiFilteredList.pop()
  }
}
for (let i = 0; i < semiFilteredList.length; i++) {
  counter = 0;
 for (let ii = 0; ii < b.length; ii++) {
   if (b[ii] % semiFilteredList[i] === 0) {
     counter+=1
   }
 }
 if (counter === b.length) {
   finalList.push(semiFilteredList[i])
 }
}
return (finalList.length)
}
```
12:12 -- Unfortunately, my current solution only passes 4 of the 9 HackerRank test cases. I'll have to explore more during my next coding session to identify where my faulty logic is.

UPDATE: I didn't get any more coding time in.
___
**Total time spent coding today**: 47 minutes

**Total time spent coding thus far in August 2019**: 4 hours 4 minutes

**Total lifetime hours of coding**: 683 hours 44 minutes