# Sunday June 23rd, 2019 Daily Coding Journal

10:21 -- While yesterday was pretty forgettable, last week as a whole was the best week I've ever had as far as programming goes. Last week I got 31+ hours of deeply focused progamming time in.

I also added a TON of algorithm explanations to my GitHub portfolio. I plan to spend the next two weeks or so continuing to grind out these algorithms and then hopefully finding full-time development work when I return to Saigon.

In any case, let's not get ahead of ourselves. Let's get started working on the [Repeated String](https://www.hackerrank.com/challenges/repeated-string/problem) algorithm.

P.S. I currently have 531 points on HackerRank which is good enough for a rank of 154,382 on HackerRank's global algorithm leaderboard.

10:30 -- It looks like for this problem we have a string *s* that is repeateded an infinite amount of times. Given that we are only evaluating the first *n* letters of the string, our job is to create a function that returns how many times the letter 'a' occured in the first *n* characters of the infinitely repeated string *s*.

10:37 -- Basic function setup:
```
function repeatedString(s, n) {

}
```
10:42 -- Halfway there...
```
function repeatedString(s, n) {
let result = '';
while (result.length < n) {
result+=s
 }
}
```
10:56 -- So, I have a solution now, but... it looks like it's not a very efficient solution. The reason I say that is because my function currently works fine if we're evaluating a small number of character (*n* < 1000).

If we evaluate a very large number of characters, however, my function has a tendancy to time out.

I'm going to refactor my code to be more efficient. Until then, however, here's my old solution:
```
function repeatedString(s, n) {
    let finalString = '';
    let result = 0;

    while (finalString.length < n) {
    finalString+=s
  }

    for (let i = 0; i < n; i++) {
        if (finalString[i] === 'a') {
        result+=1
    }
   }
 return result
}
```
11:09 -- Getting close to a new solution...
```
function repeatedString(s, n) {
let numberOfReps = n / s.length;
let initialLowerCaseACount = 0;

for (let i = 0; i < s.length; i++) {
  if (s[i] === 'a') {
initialLowerCaseACount+=1
  }
}

console.log(numberOfReps* initialLowerCaseACount)

}
```
11:23 -- I've finally solved this algorithm! Here's my final solution:
```
function repeatedString(s, n) {
let numberOfReps = Math.floor(n / s.length);
let initialLowerCaseACount = 0;
let remainderACount = 0;
for (let i = 0; i < s.length; i++) {
  if (s[i] === 'a') {
initialLowerCaseACount+=1
  }
}

if (n % s.length === 0) {
  return (numberOfReps*initialLowerCaseACount)
}
else {
  let i = 0
  while (i < n % s.length) {
    if (s[i] === 'a') {
      remainderACount+=1
    }
    i++
  }
return ((numberOfReps*initialLowerCaseACount) + remainderACount)
}

}
```
I know it looks a little bit intimidating, but I'll explain everything during my next coding session!
___
**Total time spent coding today**: 

**Total time spent coding thus far in June 2019**: 

**Total lifetime hours of coding**: 