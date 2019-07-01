# Monday July 1st, 2019 Daily Coding Journal
0:04 -- Man I'm stuck. I've worked on this algorithm for more than 2.5 hours already and I'm just not advancing any further. I'm calling it quits.
```
function saveThePrisoner(n, m, s) {
let leftovers;
let result;
if (m === n) {
leftovers = 0
}
else if (m > n) {
leftovers = m % n
}
else {
leftovers = false;
}
if (leftovers === 0) {
s - 1 > 0? result = s - 1 : result = n
return result
}
if (leftovers) {
if ((s + leftovers) <= n) {
result = (s + leftovers) -1
return result
}
else if ((s + leftovers) > n) {
result = s - leftovers + 1
return result
}
}
else {
if (leftovers === false) {
if ((s + m) <= n) {
result = (s + m) - 1
}
else {
result = s - n + m
}
return result
}
}
}
```
0:05 -- Anyway, I now have 780.7 points on HackerRank, which is good enough for a rank of 100,219 on HackerRank's global algorithm leaderboard.

0:08 -- Tomorrow I'll try to solve the [Super Reduced String](https://www.hackerrank.com/challenges/reduced-string/problem) algorithm.

0:15 -- I've committed everything from yesterday to GitHub. I'm going to commit this entry to GitHub now, and then work on some mostly non-code related stuff for the rest of the night.
___
9:09 -- I'm here. Let's start working on the 'Super Reduced String' algorithm.

9:12 -- It looks like we have a guy named Steve who has a string of lowercase characters ranging from a-z.

Anytime Steve sees two adjacent of the same letters touching each other ('aa') he deletes both letters.

Our job is to go through the string in the same manner as Steve, deleting pairs of the same letters that are touching each other.

In the end, we should return what our string looks like after all of the deletions. Or, if the final string we have is empty, we'll return 'Empty String'.

Here's our basic setup:
```
function superReducedString(s) {


}
```
9:22 -- Here's some pseduocode:
```
// create a variable updatedString.

// Loop through s as long as i is less then s.length - 1. Push the value of s[i] to updatedString.

// if s[i] === s[i+1], updatedString push s and s[i+1]. updatedString.shift() two times. Otherwise if s[i] !== s, do nothing.

// repeat, and then return whatever remains as our solution to this algorithm. If nothing remains, return 'Empty String' as our solution to this algorithm.
```
9:35 -- Almost finished...
```
function superReducedString(s) {
let updatedString = [];
for (let i = 0; i <= s.length - 1 ; i+=2) {
  console.log(`si is ${s[i]} and si+1 is ${s[i+1]}`)
  if (s[i] !== s[i+1]) {
    updatedString.push(s[i], s[i+1])
  }
}
console.log(updatedString)
}
```
9:39 -- The one thing I'm having difficulty implementing is ensuring that I don't accidentally push undefined to the end of my array *updatedString*.

9:50 -- My current solution passed 7 of the 16 test cases:
```
function superReducedString(s) {
let updatedString = [];
for (let i = 0; i <= s.length - 1 ; i+=2) {
  console.log(`i is ${i}, si is ${s[i]} and si+1 is ${s[i+1]}`)
  if (s[i] !== s[i+1]) {
    updatedString.push(s[i]
    )
    if (i + 2 <= s.length) {
      updatedString.push(s[i+1])
    }
  }
}
return (updatedString.length > 0 ? updatedString.join("") : 'Empty String');
}
```
9:51 -- Unfortunately, I think that during my next coding session I'm going to have to go back and perhaps only increment *i* by one, or do some other form of refactoring on my code.

9:52 -- Oh well, I'll see you later!
___
**Total time spent coding today**: 

**Total time spent coding in July 2019**: 

**Total lifetime hours of coding**: 