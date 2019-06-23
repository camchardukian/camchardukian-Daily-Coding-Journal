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
17:39 -- I caught up on some sleep (that I feel behind on two nights ago). I also ate a bit and worked an hour or so on another professional obligation. But forget about all that...

Let's talk about our solution for the last algorithm!

17:41 -- We have a function *repeatedString* that has two parameters: *s*: a string of lowercase English letters that a girl named Lilah has repeated an infinite amount of times, and *n*: an integer representing the first *n* number of characters in Lilah's string that are to be evaluated.

Our job is to figure out how many times the letter 'a' occurs in the first *n* characters of Lilah's string.

Here's our basic setup:
```
function repeatedString(s, n) {

}
```
17:46 -- The next thing we'll need to do is define a few variables. Those variables are *initialLowerCaseACount* initialized to 0, *remainderACount* initialized to 0, and *numberOfFullReps* initialized to the value of:
> Math.floor(n / s.length) 

To quickly go over the variables, *initialLowerCaseACount* is where we'll eventually store the value of how many times 'a' occured in the original string *s*.

This variable is NOT where we'll be storing our final result for this algorithm. If Lilah's infinitely repeated string was 'anapple', it wouldn't matter how many characters we were evaluating AKA what value was passed to *n*.

The value of *initialLowerCaseACount* in this example would be 2, because in the basic string 'anapple', the letter 'a' occurs two times.

*numberOfFullReps* counts how many times we're going to evaluate the entire basic string passed to *s*. If our string passed to *s* was apple and our number passed to *n* was 11, the entire string we would be repeating would be:
>'appleapplea'

In this example, our original string *s* is repeated in full 2 times, and it has one extra letter we're evaluating. Thus, *numberOfFullReps* would have a value of 2 in this scenario because the basic string *s* is repeated in full two times.

*remainderACount* in this scenario would have its value set to 1, because the letter 'a' occurs 1 time in the sub-section of the string not repeated in full and thus not evaluated by *numberOfFullReps*.
```
function repeatedString(s, n) {
let numberOfFullReps = Math.floor(n / s.length);
let initialLowerCaseACount = 0;
let remainderACount = 0;
}
```
Now that we've spent half a century explaining our variables, let's get to the rest of the function ;).

After our initial variable declaration and assignment phase, the next thing we're going to do is run a for loop. This for loop will iterate over all of the characters in *s*.

With each iteration of the loop, we will check to see if the current character *s[i]* is equivalent to 'a'. If so, we'll increment our variable *initialLowerCaseACount* by one.

After this loop finishes running, the value of *initialLowerCaseACount* will be equal to the number of times 'a' occurs in the basic string *s*.
```
function repeatedString(s, n) {
let numberOfFullReps = Math.floor(n / s.length);
let initialLowerCaseACount = 0;
let remainderACount = 0;
for (let i = 0; i < s.length; i++) {
  if (s[i] === 'a') {
initialLowerCaseACount+=1
  }
 }
} 
```
18:06 -- Moving forward, after we break out of our first for loop, we'll then come across an if statement. This if statement states that if *n* divided by *s.length* has a remainder of 0, we'll return *numberOfFullReps* times *initialLowerCaseACount* as our solution to this algorithm!
```
function repeatedString(s, n) {
let numberOfFullReps = Math.floor(n / s.length);
let initialLowerCaseACount = 0;
let remainderACount = 0;
for (let i = 0; i < s.length; i++) {
  if (s[i] === 'a') {
initialLowerCaseACount+=1
  }
 }

if (n % s.length === 0) {
  return (numberOfFullReps*initialLowerCaseACount)
 }
}
```
18:08 -- Of course, if *n* divided by *s.length* did have some remainder, the above would NOT be our solution to our algoritm and we'd then proceed to our else clause of our if statement.

Our else clause initializes a variable *i* to 0. It then has a while loop that will continue running for as long as *i* is less than the remainder produced by dividing *n* by *s.length*.

In simpler terms, our loop will continue running for as long as necessary to check any partial part of our *s* string that was not repeated in full, and thus could not be evaluated under *numberOfFullReps*.

With each iteration of our loop we'll increment our variable *i* after seeing whether our current character *s[i]* is equal to the string 'a'. If so, we'll increment *remainderACount* by 1, and run our for loop again if our while condition still holds true.

When we eventually break out of our for loop, we'll return (numberOfFullReps*initialLowerCaseACount) + remainderACount) as our solution to this algorithm!
```
function repeatedString(s, n) {
let numberOfFullReps = Math.floor(n / s.length);
let initialLowerCaseACount = 0;
let remainderACount = 0;
for (let i = 0; i < s.length; i++) {
  if (s[i] === 'a') {
initialLowerCaseACount+=1
  }
 }

if (n % s.length === 0) {
  return (numberOfFullReps*initialLowerCaseACount)
 }
else {
  let i = 0
  while (i < n % s.length) {
    if (s[i] === 'a') {
      remainderACount+=1
    }
    i++
  }
return ((numberOfFullReps*initialLowerCaseACount) + remainderACount)
 }
}
```
18:17 -- The explanation for this problem was a bit dense. I hope you're still with me. If so, excellent job at persisting despite this problem's level of complexity! :D

18:22 -- Wow, explaining that last algorithm was a pretty involved process. Hahaha.

Anyway, I now have 551 points which is good enough for a global rank of 148,201 on HackerRank's algorithm leaderboard.

18:25 -- During my next coding session, I'll focus on solving the [HackerRank in a String](https://www.hackerrank.com/challenges/hackerrank-in-a-string/problem) algorithm.

___
**Total time spent coding today**: 

**Total time spent coding thus far in June 2019**: 

**Total lifetime hours of coding**: 