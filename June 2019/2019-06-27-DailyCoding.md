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
**Total time spent coding today**: 

**Total time spent coding thus far in June 2019**: 

**Total lifetime hours of coding**: 