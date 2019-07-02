# Tuesday July 2nd, 2019 Daily Coding Journal

0:00 -- I just set up this journal entry for the morning. When I come to the computer in the morning, my first coding session will be dedicated to explaining the 'Gemstones' algorithm.
___
9:40 -- Let's talk about the [Gemstones](https://www.hackerrank.com/challenges/gem-stones/problem) algorithm.

9:42 -- It looks like we have a boy named Josh that has a rock collection. Each rock consists of different minerals.

Minerals are represented using lowercase letters (a-z).

A mineral is considered a gemstone if it occurs at least once in each of the rocks in John's collection.

Given an array *arr*, our job is to create a function *gemstones* that returns an integer representing the number of gemstones found in John's collection.

Here's our basic setup:
```
function gemstones(arr) {

}
```
9:43 -- Now that we've got some background information and the "skeleton" of our function setup, let's declare some variables.

My solution for this algorithm is going to require several variables including:

* *gemstoneCount*: Initialized to 0, this variable will be an integer representing the number of gemstones we have. We'll eventually return this variable as our solution to this algorithm.

* *isGemstone*: A boolean that states whether our current mineral is a gemstone or not. We'll initiate this variable to true.

* *alreadyEvaluated*: An array of (in most cases) strings representing the minerals we've already evaluated and thus don't need to do any further testing on, even if we have multiple instances of said minerals later on. We'll initialize this variable to an empty array.

Here's the actual code for what we were talking about above:
```
function gemstones(arr) {
  let gemstoneCount = 0
  let isGemstone = true;
  let alreadyEvaluated = []
}
```
9:51 -- Next, we need a for loop to loop through all of the minerals in our first rock.
```
function gemstones(arr) {
  let gemstoneCount = 0
  let isGemstone = true;
  let alreadyEvaluated = []
for (let i = 0; i < arr[0].length; i++) {
    }
}
```
9:53 -- Each time our for loop runs it's going to do a few things. First, it's going to set the value of *isGemstone* to true.

The reason we're doing this is because we're going to assume a given mineral occurs in every rock and is a gemstone unless the tests we conduct later on show otherwise.

We're also going to check whether we've already tested whether a certain mineral was a gemstone or not.

This is necessary because a given mineral could theoretically occur dozens, hundreds,or even millions of times in a single rock.

Yet, a given mineral can only be a gemstone once because the criteria for a gemstone mineral (according to the algorithm's instructions) is simply one that occurs in each rock at least once.

No importance is given to whether a mineral occurs multiple times within our rocks.

Thus, we want to make our function more efficient and save lots of processing power by only checking each mineral one time.

We can do this by pushing any mineral we've already tested to an array *alreadyEvaluated*, and only conducting further testing on a mineral if it doesn't occur in that array (alreadyEvaluated.indexOf(arr[0][i]) < 0) and thus isn't a mineral we've already spent time looking at.
```
function gemstones(arr) {
  let gemstoneCount = 0
  let isGemstone = true;
  let alreadyEvaluated = []
for (let i = 0; i < arr[0].length; i++) {
  isGemstone = true
  if (alreadyEvaluated.indexOf(arr[0][i]) < 0) {
  }
 }
}
```
10:02 -- The last thing we need is our nested for loop. Our nested for loop will take the mineral (letter) provided by our outer for loop.

Our nested for loop will then start at the 1 index of *arr* (we're starting at 1 because the 0th index is where we're pulling minerals from, and thus doesn't need to be tested).

Our nested for loop will iterate through each "rock" in *arr*, evaluating whether each rock contains a given mineral: *if arr[ii].indexOf(arr[0][i]) < 0*.

If at any time the given mineral does not occur within one of our rocks, we'll set *isGemstone* to false.

We'll then break out of our for loop and push the just evaluated mineral to our array *alreadyEvaluated*.

If, however, we get through our entire array and *isGemstone* retains its initial value of true, we'll break out of our for loop and increment *gemstoneCount* by one (because the mineral we just looked at was a gemstone), before pushing the mineral we just looked at to *alreadyEvaluated*.

We'll then repeat all of the steps from before, continuing until we eventually break out of BOTH of our for loops.

When that occurs, we'll return *gemstoneCount* as our solution to this algorithm!
```
function gemstones(arr) {
  let gemstoneCount = 0
  let isGemstone = true;
  let alreadyEvaluated = []
for (let i = 0; i < arr[0].length; i++) {
  isGemstone = true
  if (alreadyEvaluated.indexOf(arr[0][i]) < 0) {
  for (let ii = 1; ii < arr.length; ii++)
  {
    if (arr[ii].indexOf(arr[0][i]) < 0) {
      isGemstone = false
    }
   }
  if (isGemstone === true) {
    gemstoneCount+=1
   }
  alreadyEvaluated.push(arr[0][i])
  }
 }
return gemstoneCount
}
```
10:10 -- You're done! This was a bit of a lengthy explanation, but I hope you were able to get some value out of it. Way to go!

10:18 -- I just finished committing the 'Gemstones' algorithm to GitHub. I now have 830.7 points, which is good enough for a rank of 93,833 on HackerRank's global algorithm leaderboard.

10:19 -- I'd like to solve at least one more algorithm in order to get my "gold badge" on HackerRank as I'm just 20 points away from doing so.

For that reason, during my next coding session I'll try to solve the [ACM ICPC Team](https://www.hackerrank.com/challenges/acm-icpc-team/problem) algorithm on HackerRank.

Then, maybe I'll finally move on to the data structure problems on HackerRank...
___
16:21 -- Caught up on some sleep, amongst other things. Let's get to solving the 'ACM ICPC Team' algorithm.

16:22 -- It looks like we have some people attending the ACM-ICPC World Finals (a programming contest).

Given a list of topics known by each attendee (zeros represent not known while ones represent known), determine the maximum numbers of topics a 2-person team can know.

We also need to determine how many different ways a team could be formed that would know the maximum number of topics we just calculated.

We have a function *acmTeam* that has a single parameter *topic*, which takes in a string of binary digits.

Here's our basic setup:
```
function acmTeam(topic) {

}
```
16:37 -- One thing I was initially a little bit confused by was whether we were receiving a string, or array of binary digits.

I've since used the console to determine *topic* is indeed an array of integers.

I'll document more of my progress as I actually have something more concrete to show.

16:44 -- It's not much, but here's where I'm at now:
```
function acmTeam(topic) {
let result = [];
for (let i = 0; i < topic.length; i++) {
  for (let ii = 0; ii < topic[i].length; ii++) {
    console.log(`we are on person number ${i} and topic number ${ii}`)
  }
 }
}
```
16:49 -- Just trying to visualize everything at this point:
```
function acmTeam(topic) {
let result = [];
for (let i = 0; i < topic.length; i++) {
  for (let ii = i + 1; ii < topic.length; ii++) {
    for (let j = 0; j < topic[i].length; j++) {
    console.log(`person number ${i} and person number ${ii} and topic ${j} `)
    }
  }
 }
}
```
16:55 -- Well on my way to the solution...
```
function acmTeam(topic) {
let highestTopicsKnown = 0;
let numberOfTopTeams = 0;
let currentTopicsKnown = 0;
for (let i = 0; i < topic.length; i++) {
  for (let ii = i + 1; ii < topic.length; ii++) {
      currentTopicsKnown = 0
    for (let j = 0; j < topic[i].length; j++) {
    console.log(`person number ${i} and person number ${ii} and topic ${j} `)
    if (topic[i][j] === '1' || topic[ii][j] === '1') {
      currentTopicsKnown+=1
    }
   }
   console.log(`person ${i} and person ${ii} knew ${currentTopicsKnown} topics`)
  }
 }
}
```
17:02 -- I has a solution that passed 3 out of the 9 test cases. The test cases it didn't pass seem to be due to performance issues and timeouts.

Because I know I'm on the right track, I'm going to delete all my console.log() statements and see if that improves my performance at all.

17:03 -- Sure enough, removing the console.log() statements for better performance was exactly what we needed!

Heres's my solution that passes all of the test cases:
```
function acmTeam(topic) {
let highestTopicsKnown = 0;
let numberOfTopTeams = 0;
let currentTopicsKnown = 0;
for (let i = 0; i < topic.length; i++) {
  for (let ii = i + 1; ii < topic.length; ii++) {
      currentTopicsKnown = 0
    for (let j = 0; j < topic[i].length; j++) {
    if (topic[i][j] === '1' || topic[ii][j] === '1') {
      currentTopicsKnown+=1
    }
   }
   if (currentTopicsKnown > highestTopicsKnown) {
     highestTopicsKnown = currentTopicsKnown
     numberOfTopTeams = 1
   }
   else if (currentTopicsKnown === highestTopicsKnown) {
     numberOfTopTeams +=1
   }
  }
 }
 return [highestTopicsKnown, numberOfTopTeams]
}
```
17:04 -- At this point, I'm feeling a bit tired out. I'm going to take a break and maybe do a little exercise before coming back and explaining my solution to this algorithm.


___
**Total time spent coding today**: 

**Total time spent coding thus far in July 2019**: 

**Total lifetime hours of coding**: 