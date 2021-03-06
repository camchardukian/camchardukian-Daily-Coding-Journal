# Thursday June 27th, 2019 Daily Coding Journal

0:00 -- Picking right back up where we left off in yesterday's journal entry -- trying to solve the [Picking Numbers](https://www.hackerrank.com/challenges/picking-numbers/problem) algorithm on HackerRank.

0:25 -- Still going... After a lot of searching I noticed that there's two 55s and a 56 in this array. That should give us an array length of 3... but something funky is going on.

For whatever reason, I'm only getting an array of [56, 55] rather than [56, 55, 55].

0:36 -- Well now I have a really weird bug. I added a console.log() to my function and now it's returning the right integer answer (but only by coincidence). Whaaat? :p

0:47 -- I'm so exhausted. I'm no longer thinking clearly. I'm a little bit frustrated because my solution seems to work fine for 12 of the 13 test cases, but it's kind of funky on this one.

I've been playing around with things, and now things don't even look right to me. I think I messed my code up when I was experimenting with it.
```
function pickingNumbers(a) {
let result = 0;
let testArray = [];
let groupAbsolChecker = true
for (let i = 0; i < a.length; i++) {
testArray = []

for (let ii = 0; ii < a.length; ii++) {

if (ii !== i) {
if (Math.abs(a[i] - a[ii]) <= 1) {
if (testArray.length > 0) {
groupAbsolChecker = true
for (let j = 0; j < testArray.length && groupAbsolChecker === true; j++) {
if (groupAbsolChecker === true) {
if (Math.abs(testArray[j] - a[ii]) > 1 ) {
groupAbsolChecker = false
}
}
}
}
else {
testArray.push(a[ii])
}
if (groupAbsolChecker === true) {testArray.push(a[ii])}
}
}
}
if (testArray.length > result) {
result = testArray.length
}
}
return result
}
```
0:50 -- Hopefully this problem will incubate in my head and I'll be able to solve it if I come at things with a clear head tomorrow.

It's late, I'm going to commit yesterday's entry and today's to GitHub before calling it a day.

0:57 -- See you tomorrow!
___
9:19 -- I got a little bit of sleep. Let's try to solve this problem now again.

9:26 -- I'm going to try rebuilding everything from scratch for a different perspective:
```
function pickingNumbers(a) {
for (let i = 0; i < a.length; i++) {
  if (Math.abs(a[0] - a[i]) <= 1) {
    console.log('less')
  }
  else {
    console.log('more')
  }
 }
}
```
9:33 -- Moving forward...
```
function pickingNumbers(a) {
let longestArrayOfAbsols = [];
let currentArray = []

for (let i = 0; i < a.length; i++) {
  currentArray = [];
  for (let ii = 0; ii < a.length; ii++){
      if (Math.abs(a[i] - a[ii]) <= 1) {
        console.log(Math.abs(a[i] - a[ii]))
        currentArray.push(a[ii])
      }
    }
    console.log(currentArray)
 }
}
```
9:52 -- I don't know why, but I just can't seem to figure out this problem.

10:01 -- I'm banging my head against the wall and not getting anything out of this algorithm anymore.

10:02 -- I now have 698.5 points, which is good enough for a rank of 113,641 on HackerRank's global algorithm leaderboard.

During my next coding session, I'll try to solve the [Alternating Characters](https://www.hackerrank.com/challenges/alternating-characters/problem) algorithm.

For now, however, I'm going to take a break and try to let go of some of this frustration.
___
16:57 -- Let's try to knock out the next algorithm.

16:59 -- It looks like we have a function *alternatingCharacters* that has a single parameter *s* which takes in a string.

Our string will be a series of  consecutive 'A' and 'B' characters.

We will then "delete" characters from our string such that we no longer have any 'A' characters that are "touching" any other 'A' characters nor any 'B' characters that are touching any other 'B' characters.

Our goal is to determine the minimum number of deletions required to achieve the above.

Here's our basic function setup:
```
function alternatingCharacters(s) {

}
```
17:05 -- From here on out, I'll work to solve this algorithm, documenting my progress along the way.

After reaching a final solution, I'll then explain said solution to you.

17:10 -- Oh wow, I literally solved this algorithm in less than 5 minutes lol. Not banging my head against the wall for the first time in two days was so refreshing hahaha.

17:12 -- Let me explain how I came to my solution. Hopefully you'll be understand this algorithm as easily as I was able to! :D

17:13 -- It looks like we have a function *alternatingCharacters* that has a single parameter *s* which takes in a string.

Our string will be a series of  consecutive 'A' and 'B' characters.

We will then "delete" characters from our string such that we no longer have any 'A' characters that are "touching" any other 'A' characters nor any 'B' characters that are touching any other 'B' characters.

Our goal is to determine the minimum number of deletions required to achieve the above.

Here's our basic function setup:
```
function alternatingCharacters(s) {

}
```
17:15 -- My logic for solving this algorithm was pretty simple. The first thing I did was declare a variable *counter*.

I initialized this variable to **0**. The purpose of *counter* is to act as a location where we can store the value of how many deletions we need to make.

Anytime we see that a deletion needs to occur, we can increment the value of *counter* by 1.
```
function alternatingCharacters(s) {
  let counter = 0;
    counter+=1
}
```
17:16 -- Of course, we're not finished yet. Right now our code is somewhat nonsensical. We initialize *counter* to 0, and increment it for seemingly no reason.

We need to define some kind of criteria so that we know when a deletion needs to occur.

My thinking was that a deletion will need to occur anytime our first character is equal to the character immediately after it.

For example, let's say we're given this string:

> ABBABAA

We would look at the 1st character 'A', and then look at the character following it (the 2nd character in our string) 'B'. Since they are not the same, we'd simply proceed to the next pair of characters.

Is the 2nd character in our string 'B' equal to the 3rd character in our string 'B'? YES! Because this is true, we know we'd need to make a deletion.

Thus, we'd increment *counter* by 1, and we can imagine the string as now being:

> AB(the 2nd B is deleted)ABAA ------ Or if it's easier for you to see: ABABAA

We'd then repeat our process until we reaching the 2nd to last character with the final character in our string.

It isn't necessary of course to compare the final character in our string with the character that follows it because no such character exists. Thus, we'd simply be comparing the final character with undefined with is simply a waste of resources.

Thus, we go through all of our looping incrementing *counter* as necessary. When we eventually break out of our loop, we can return *counter* as our solution to this algorithm!
```
function alternatingCharacters(s) {
  let counter = 0;
for (let i = 0; i < s.length - 1; i++) {
  if (s[i] === s[i+1]) {
    counter +=1
  }
 }
return counter
}
```
17:26 -- Hopefully my explanation of my solution for this algorithm was clear to you. Good for you on reading through the entire explanation! :D

17:38 -- I'm glad I was able to solve that last algorithm pretty easily. It helped me get my confidence back hahaha.

In any case, I now have 718.5 points on HackerRank, which is good enough for a rank of 110,034 on HackerRank's global algorithm leaderboard.

A couple more algorithms and I'll be in the top 100,000! :D

17:40 -- During my next coding session I'll work to solve the [Pangrams](https://www.hackerrank.com/challenges/pangrams/problem) algorithms.
___
21:57 -- I'm back. I just finished getting dinner with my family, exercising, and doing a bit of socializing. Now, it's time to work on the next algorithm.

22:00 -- It seems we have a boy named Roy who wants to improve his typing speed. For that reason, he wants to practice typing pangrams (a single sentence which contains every letter of the alphabet).

We have a function *pangrams* that has a single parameter *s*, which will take in a string.

We need to evaluate whether the string *s* is a pangram -- ignoring cases (whether the letters are lower or uppercase).

Here's our basic setup:
```
function pangrams(s) {

}
```
22:14 -- Progress...
```
function pangrams(s) {
  let inProgress = true;
s = s.toLowerCase();
const alphabet =
  { 'a': 1,
   'b': 2,
   'c': 3,
   'd': 4,
   'e': 5,
   'f': 6,
   'g': 7,
   'h': 8,
   'i': 9,
   'j': 10,
   'k': 11,
   'l': 12,
   'm': 13,
   'n': 14,
   'o': 15,
   'p': 16,
   'q': 17,
   'r': 18,
   's': 19,
   't': 20,
   'u': 21,
   'v': 22,
   'w': 23,
   'x': 24,
   'y': 25,
   'z': 26
  }

  while (inProgress === true) {
for (let i = 0;)
  }
}
```
22:17 -- Just realized I switched the keys and values in my *alphabet* object. Bummer. Well, I deserve this for my laziness.

I'll go look up the code to see the numbers for the different html-8 characters.

Ahh... [ASCII](http://www.asciitable.com/). That's what I was thinking about.

22:26 -- I'm wondering whether I need to remove the spaces from this string to loop over it more efficiently...
```
function pangrams(s) {
  let inProgress = true;
s = s.toLowerCase();

for (let i = 0; i < s.length; i++) {
console.log(`${s[i]}`.charCodeAt(0));
  }
 }
```
22:32 -- Getting close...
```
function pangrams(s) {
  let inProgress = true;
s = s.replace(/\s/g, "");
s = s.toLowerCase();

for (let i = 0; i < s.length; i++) {
console.log(`${s[i]}`.charCodeAt(0));
  }
 }
```
22:49 -- Gotta clean up a little bit of stuff, but I'm almost finished.
```
function pangrams(s) {
  let inProgress = true;
  let result;
s = s.replace(/\s/g, "").toLowerCase().split("");
let testArray = s.map(s => s.charCodeAt(0))

  for (let i = 97; i <= 122; i++) {
    if (testArray.indexOf(i) > -1) {
      console.log("true")
    }
    else {
      result = "not a pangram"
      return result
    }
  }
result = 'mfanofdjnwon'
 }
```
22:54 -- I've passed all the test cases! Here's my final solution:
```
function pangrams(s) {
  let result = 'pangram';
s = s.replace(/\s/g, "").toLowerCase().split("");
let testArray = s.map(s => s.charCodeAt(0))

  for (let i = 97; i <= 122; i++) {
    if (testArray.indexOf(i) > -1) {

    }
    else {
      result = "not pangram"
      return result
    }
  }
return result
}
```
22:55 -- I need to take a break now. I'm going to stetch my body, maybe get a snack, and then I'll come back and explain my solution to you during my final coding session of the day! :D
___
23:28 -- I'm back. Let's get this algorithm explained, commit everything to GitHub, and then call it a night.

23:29 -- It seems we have a boy named Roy who wants to improve his typing speed. For that reason, he wants to practice typing pangrams (a single sentence which contains every letter of the alphabet).

We have a function *pangrams* that has a single parameter *s*, which will take in a string.

We need to evaluate whether the string *s* is a pangram -- ignoring cases (whether the letters are lower or uppercase).

Here's our basic setup:
```
function pangrams(s) {

}
```
23:30 -- We need to declare and initalize a few variables. The most simple of which is a variable we can name *result*. We'll initialize *result* to the string 'pangram'.

You'll probably find understanding this variable pretty straightforward. *result* is simple a variable that will hold the value 'panagram' or 'not panagram'. 

We'll later return our variable *result* as our solution to this algorith.

We also need to get rid of the spaces in our string *s*, ensure all of the characters in *s* are lowercase, and then we'll also want to turn *s* into an array.

More on that coming up shortly...
```
function pangrams(s) {
  let result = 'pangram';
s = s.replace(/\s/g, "").toLowerCase().split("");
}
```
23:35 -- Now, the next thing we need to do is declare another variable *testArray*. 

The purpose behind creating *testArray* is we want an array that contains [ASCII numbers/codes](https://en.wikipedia.org/wiki/ASCII) (in practical terms each item in our array will be an integer), that correspond with each character in our string.

We can do this by mapping the character code from each character in our string over to our new array.
```
function pangrams(s) {
let result = 'pangram';
s = s.replace(/\s/g, "").toLowerCase().split("");

let testArray = s.map(s => s.charCodeAt(0))
```
23:43 -- Next, we need a for loop. This loop will iterate through all of the ASCII codes from lowercase 'a' (97) all the way to 'z' (122).

Each time through our array, we'll use the indexOf() method on *testArray* to see if *testArray* contains the ASCII code we're looking for.

For example, if testArray.indexOf(97) returns any value greater than -1, we'll know that ASCII code occured somewhere in our array, and thus... somewhere in our string we have the letter that corresponds to that ASCII code ('a').

If testArray.indexOf(i) is NOT greater than -1, however, we'll know *testArray* does not contain the ASCII code we're looking for.

Moreover, we'll know our string is not a pangram because it is missing some letter between 'a' and 'z'. At this point you probably also understand why we had to convert our entire string to lowercase at the beginning of our function:

> We needed to ensure all of the ASCII codes we were looking for would appear in consecutive orders, and that we would not miss some code because we were for example searching for ASCII code 65 ('A'), when the reality is that *testArray* only contained ASCII code 97 ('a').

To make a long story short, if our string contains all the ASCII codes we need, we'll return *result* in its current form as the solution to our algorithm ('pangram').

If at any point along the way, however, *testArray* doesn't contain the ASCII code we're looking for... we'll set the value of *result* to the string 'not pangram' and then return *result* as our solution to this algorithm.
```
function pangrams(s) {
let result = 'pangram';
s = s.replace(/\s/g, "").toLowerCase().split("");

let testArray = s.map(s => s.charCodeAt(0))

  for (let i = 97; i <= 122; i++) {
    if (testArray.indexOf(i) > -1) {

    }
    else {
      result = "not pangram"
      return result
    }
  }
return result
}
```
23:54 -- That was a LONG explanation for less than 20 lines of code hahahaa. In any case, I hope you got some value out of this explanation.

Keep up the great coding! :D

23:59 -- I'll see you in tomorrow's entry!


___
**Total time spent coding today**: 4 hours 10 minutes

**Total time spent coding thus far in June 2019**: 71 hours 4 minutes

**Total lifetime hours of coding**: 642 hours 47 minutes