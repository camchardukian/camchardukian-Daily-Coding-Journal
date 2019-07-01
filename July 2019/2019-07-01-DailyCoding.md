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
10:41 -- I'm back. Let's try to solve things again.

10:59 -- I'm quite lost trying to figure out how I should be using the slice() method to solve this algorithm.
```
function superReducedString(s) {
  let array = s.split("");
for (let i = 0; i < s.length; i++) {
  if (array[i] === array[i+1]) {
array = array.slice(i, i+2)
  }
} 
  console.log(array)
}
```
11:13 -- I've finally solved the algorithm! Here's my final solution:
```
function superReducedString(s) {
  let array = s.split("");
  let b = 0
for (let i = 0; i < array.length; i++) {
  if (array[i] === array[i + 1]) {
 array.splice(i, 2)
 i = -1;
  } 
}
return (array.length > 0? array.join(""): 'Empty String')
}
```
11:14 -- During my next coding session I'll format my code a little bit more cleanly, and explain my solution to you.
___
17:51 -- Let's talk about the Super Reduced String algorithm. It looks like we have a guy named Steve who has a string of lowercase characters ranging from a-z.

Anytime Steve sees two adjacent of the same letters touching each other ('aa') he deletes both letters.

Our job is to go through the string in the same manner as Steve, deleting pairs of the same letters that are touching each other.

In the end, we should return what our string looks like after all of the deletions. Or, if the final string we have is empty, we'll return 'Empty String'.

Here's our basic setup:
```
function superReducedString(s) {

}
```
17:54 -- Next, I'm going to declare a variable *array*. We'll initialize *array* to the value of *s*.split("").

The reason we're doing this is because later on we'll want to use the splice() method. Doing so requires an array, and thus we need to manipulate our data types ahead of time.
```
function superReducedString(s) {
  let array = s.split("");
}
```
17:57 -- Moving forward, the next thing we need is a loop. This loop will have a variable *i* initialized to 0, and will run for as long as *i* is less than the length of our array.

Each time we go through our loop we'll increment *i* by one.

Also, if *array[i]* (some item in our array) is ever equal to *array[i+1]* (the item immediately following the previous item we just mentioned), we're going to do something.

We'll talk about that in the next step.
```
function superReducedString(s) {
  let array = s.split("");
for (let i = 0; i < array.length; i++) {
  if (array[i] === array[i + 1]) {
  } 
 }
}
```
18:01 -- So, what's the something we're doing to do if *array[i]* is equal to *array[i+1]*? It's simple.

We're going to take our array, and splice it starting at *i*, and splicing for a duration of two items.

This enables us to remove items from our array, without having "empty" items in our array as would be the case if we used the delete keyword.

After using the splice() method, we'll set the value of *i* equal to -1. This ensures that when our loop runs again, after *i* is incremented it will have a value of 0 (-1 + 1 === 0).

The reason we want *i* to have a value of 0 is that after using the splice() method, we may have new combinations of letters touching each other.

Thus, we need to go and loop through all of *array* again to see if there are any new or remaining adjacent letters that are equal to each other.
```
function superReducedString(s) {
  let array = s.split("");
for (let i = 0; i < array.length; i++) {
  if (array[i] === array[i + 1]) {
 array.splice(i, 2)
 i = -1;
  } 
 }
}
```
18:08 -- Eventually, we'll no longer have any adjacent letters that are equal to each other and we'll be able to finish looping through our variable *array*.

When this happens, we'll break out of our loop.

At this point we'll then return the result of our ternary operator as our solution to this algorithm!

If the length of *array* is greater than 0,it means we have some letters that we weren't able to "remove" from our array.

If this is the case, we'll use the .join() method on our array (because the algorithm wants our solution to be of the string data type rather than an array) and return that as our solution to this algorithm.

Otherwise, if the length of our array is 0, we'll return 'Empty String' as our solution to this algorithm.
```
function superReducedString(s) {
  let array = s.split("");
for (let i = 0; i < array.length; i++) {
  if (array[i] === array[i + 1]) {
 array.splice(i, 2)
 i = -1;
  } 
 }
return (array.length > 0? array.join(""): 'Empty String')
}
```
18:14 -- I found this algorithm to be a little bit challenging, but hopefully my algorithm solution and explanation helped clear some things up for you.

Keep working hard everyday and you and your developer skills are sure to improve! :D

18:19 -- I just finished committing the Super Reduced String algorithm to GitHub.

18:20 -- I now have 790.7 points, which is good enough for a rank of 98,841 on HackerRank's global algorithm leaderboard.

18:22 -- During my next coding session, I'll try to solve the [Halloween Sale](https://www.hackerrank.com/challenges/halloween-sale/problem) algorithm.

___
**Total time spent coding today**: 

**Total time spent coding in July 2019**: 

**Total lifetime hours of coding**: 