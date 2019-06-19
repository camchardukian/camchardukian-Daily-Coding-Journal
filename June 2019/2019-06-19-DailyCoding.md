# Wednesday June 19th, 2019 Daily Coding Journal

9:37 -- Looks like we're not getting a particularly early start today. I can't complain though, the last 2 days I've gotten almost 12.5 hours of coding in!

I'm going to shoot for another 6 hours of coding today. It's a tough target, but one I feel super proud when I actually hit it.

In any case, let't begin!

9:38 -- I currently have 296 points on HackerRank which is good enough for a global rank of 272,397. Let's go and solve the Birthday Chocolate algorithm!

9:40 -- It looks like in this problem we have a girl named Lily who wants to share a chocolate bar with Ron for his birthday.

The chocolate bar has numbers printed on each of its squares. Lily wants to take consecutive squares from the chocolate bar that sum up to be Ron's birthday, and that have a length property (think how many total pieces) equal to Ron's birth month.

I'm going to work on solving this problem, I'll document my progress along the way, and then I'll explain my solution after solving this algorithm.

9:49 -- Initial problem setup:
```
function birthday(s, d, m) {

}
```
9:55 -- Baby steps...
```
function birthday(s, d, m) {
for (let i = 0; i < s.length; i++) {
  console.log(`current is ${s[i]} and previous is ${s[i-1]}`)
}
}
```
9:59 -- Taking a quick break. Back shortly.

10:26 -- I'm back. Let's finish solving this problem.

10:30 -- I'm feeling so confused. I think I'm going to delete everything and start from scratch.

10:31 -- Let's try to write pseudocode, to break things down and make this problem more manageable.

10:39 -- Here's my pseudocode:
```
// initialize approvedGroups variable to empty array.
// initialize counter variable to 0
// initialize currentGroup variable to an empty array
// loop through all of the numbers in *s* array
// update currentGroup variable to an empty array
// push s[i] to currentGroup variable
// set counter equal to s[i]
// use a nested for loop.
// Nested for loop increments counter by s[ii]
// s[ii] is pushed to current group
// break out of nested for loop.
// If counter equals *d* and currentGroup[0].length equals m, push currentGroup[0] to approvedGroups
// repeat??
```
It was starting to get a bit obscure by the end, but let me try to implement it and if anything is off it'll then be easier to see :)

10:48 -- It's coming along...
```
function birthday(s, d, m) {
let approvedGroups = [];
let currentGroup = [];
let counter = 0;

for (let i = 0; i < s.length; i++) {
  currentGroup = [];
  currentGroup.push(s[i])
  counter = s[i];
 for (let ii = i + 1; ii < s.length && currentGroup.length < m; ii++) {
   console.log(s[ii])
 }
}
}
```

10:54 -- I finally solved this algorithm. Here's my final solution:
```
function birthday(s, d, m) {
let approvedGroupCount = 0;
let currentGroup = [];
let counter = 0;

for (let i = 0; i < s.length; i++) {
  currentGroup = [];
  currentGroup.push(s[i])
  counter = s[i];
 for (let ii = i + 1; ii < s.length && currentGroup.length < m; ii++) {
   counter+=s[ii];
   currentGroup.push(s[ii])
 }
 console.log(counter)
 console.log(currentGroup)
 if (counter === d && currentGroup.length === m) {
   approvedGroupCount+=1
 }
}
return approvedGroupCount
}
```
I can't believe this problem was only worth 10 points. It was quite a handful haha. 

UPDATE: I knew my solution wasn't optimized, so I asked myself how I could optimize things. Follow my explanation below for my improved solution that builds off the initial solution.


10:58 -- Let's explain this algorithm step-by-step. To start, we have a function *birthday* which has three parameters *s*, *d*, and *m*.

*s* is an array of integers representing the numbers printed on our squares of chocolate.

*d* is an integer representing Ron's birthday (which the sum of our chocolates must equal).

*m* is an integer representing Ron's birth month (which the length property of our result or "number of chocolates given" must match).
```
function birthday(s, d, m) {

}
```
11:01 -- Moving forward, I've also created a few variables. *approvedGroupCount* initialized to 0, *currentGroup* initialized to an empty array, and *counter* initialized to 0.
```
function birthday(s, d, m) {
let approvedGroupCount = 0;
let currentGroup = [];
let counter = 0;
}
```
11:05 -- Next, we use a for loop to loop through all of the values in our *s* array as long as (s.length - i ) is greater than or equal to m.

This piece of logic is important because it prevents unnecessary looping after we no longer have enough chocolate squares left to satisfy Lily's desire of giving Ron a number of chocolate squares equal to his birth month.

We also reset our current group to an empty array, push the value of *s[i]* to *currentGroup* and set *counter* equal to *s[i]*.

Some of these steps may seem unnecessary now, however, that's simply because we haven't yet implemented our nested for loop.
```
function birthday(s, d, m) {
let approvedGroupCount = 0;
let currentGroup = [];
let counter = 0;

for (let i = 0; i < s.length && (s.length - i) >= m ; i++) {
  currentGroup = [];
  currentGroup.push(s[i])
  counter = s[i];
```
11:10 -- Now, time for the nested for loop. Our nested for loop will start at the chocolate bar after the current bar (let ii = i + 1), and will continue to run as long as we still have chocolate bars (ii < s.length) AND the number of chocolate bars we currently have (the ones we're considering giving to Ron) is less than Ron's birth month ((currentGroup.length < m)), with *ii* being incremented by one each time through the loop.

With each iteration of the loop, we'll increment counter by *s[ii]* and push *s[ii]* to our *currentGroup* array.
```
function birthday(s, d, m) {
let approvedGroupCount = 0;
let currentGroup = [];
let counter = 0;

for (let i = 0; i < s.length && (s.length - i) >= m ; i++) {
  currentGroup = [];
  currentGroup.push(s[i])
  counter = s[i];
 for (let ii = i + 1; ii < s.length && currentGroup.length < m; ii++) {
   counter+=s[ii];
   currentGroup.push(s[ii])
 }
}
```
11:18 -- Finally, after we break out of our nested for loop, we'll evaluate whether *counter* is equal to *d*, and *currentGroup.length* is equal to m.

If so, we know that the given combination of chocolate bars is valid, and we increment *approvedGroupCount* by one.

After that, we'll go back to our previous loops and repeat the process. After all of our looping has eventually finished, we'll return *approvedGroupCount* as our solution to this algorithm.
```
function birthday(s, d, m) {
let approvedGroupCount = 0;
let currentGroup = [];
let counter = 0;

for (let i = 0; i < s.length && (s.length - i) >= m ; i++) {
  currentGroup = [];
  currentGroup.push(s[i])
  counter = s[i];
 for (let ii = i + 1; ii < s.length && currentGroup.length < m; ii++) {
   counter+=s[ii];
   currentGroup.push(s[ii])
 }
 if (counter === d && currentGroup.length === m) {
   approvedGroupCount+=1
 }
}
return approvedGroupCount
}
```
Wow, that was a dense explanation! Well done for following along! :D

11:25 -- Finally got the birthday chocolate algorithm out of the way. I now have 306 points on HackerRank which is good enough for a global rank of 264,145.

11:27 -- In my next coding session I'll tackle the [Jumping on the Clouds: Revisited](https://www.hackerrank.com/challenges/jumping-on-the-clouds-revisited/problem) algorithm.
___
12:22 -- Went through my morning routine, did some house work, now let's work on the next challenge!

12:24 -- We've got a girl named Aerith who is playing a cloud hopping game. Her character's energy starts at 100. It looks like it takes 1 unit of energy to jump from cloud to cloud. But, if her character lands on a thundercloud her character will lose an additional two units of energy.

Our job is to figure out how much energy Aerith will have after all of her jumps.

As usual, I'll document my progress as I go about solving this algorithm, and explain everything in more detail after I reach a final solution.

12:33 -- initial setup:
```
function jumpingOnClouds(c, k) {
console.log(c, k)
}
``` 

12:37 -- A little progress...
```
function jumpingOnClouds(c, k) {
  let energy = 100;
for (let i = 0; i < c.length; i+=k) {
  console.log(c[i])
}
}
```

12:39 -- Wow, I'm finished already:
```
function jumpingOnClouds(c, k) {
  let energy = 100;
for (let i = 0; i < c.length; i+=k) {
  if (c[i] === 1) {
    energy-=3
  }
  else {
    energy -=1
  }
}
return energy
}
```
12:40 -- First, we have a function *jumpingOnClouds* that has two parameters: *c*: an array of integers representing the different cloud types, and *k*: an integer representing the length of one jump.

I've also initialized a variable *energy* to 100, because our character energy starts at 100 per the algorithm instructions.
```
function jumpingOnClouds(c, k) {
  let energy = 100;
}
```
12:44 -- Next, we use a for loop to iterate through our array of clouds *c*. We continue as long as our incrementor *i* is less than the length of our clouds array, also keeping in mind that we're incrementing *i* by the value of *k* or how far our character is capable of jumping.

For each iteration of our array, we identify whether our character landed on a thundercloud (1) or a safe cloud (0). We do this by seeing whether the current array item c[i] is equal to 1.

If so, we know our character landed on a thundercloud and we decrement *energy* by three. Otherwise, we only decrement *energy* by one because we know we're simply dealing with a standard jump onto a normal or safe cloud.

After we've iterated through the entire array and break out of our loop, we return *energy* as our solution to this algorithm!
```
function jumpingOnClouds(c, k) {
  let energy = 100;
for (let i = 0; i < c.length; i+=k) {
  if (c[i] === 1) {
    energy-=3
  }
  else {
    energy -=1
  }
}
return energy
}
```
12:57 -- We made pretty quick work of that last algorithm. I now have 321 points on HackerRank which is good enough for a global rank of 252,914.

12:58 -- In my next coding session I'll solve the [Find Digits](https://www.hackerrank.com/challenges/find-digits/problem) algorithm.
___
**Total time spent coding today**: 

**Total time spent coding thus far in June 2019**: 

**Total lifetime hours of coding**: 