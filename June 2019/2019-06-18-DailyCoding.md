# Tuesday June 18th, 2019 Daily Coding Journal

7:23 -- Here we go -- getting an early start today. Let's try to solve the [Designer PDF Viewer](https://www.hackerrank.com/challenges/designer-pdf-viewer/problem) that we were a bit too tired to solve last night.

7:29 -- I wonder if the Object.entries() method would be useful for what I'm trying to do...

7:33 -- I'm thinking that in combination with the Object.entries() method I could perhaps use a nested for loop. The first for loop would loop through our array of letters and push a height to them based on the values passed as an argument to the *h* array.

The second for loop would to find the height of the current letter in our word, eventually looping through the entire word.

If the letter was taller than any of the previous words, we could save in a *tallestLetter* variable.

Otherwise, we could move on to the next letter.

7:46 -- I feel like I'm finally making progress with this problem:
```
function designerPdfViewer(h, word) {
  let alphaArr = [
 ['a'], ['b'], ['c'], ['d'], ['e'],['f'], ['g'],
 ['h'], ['i'], ['j'], ['k'], ['l'], ['m'], ['n'], ['o'], ['p'], ['q'], ['r'], ['s'], ['t'], ['u'],
 ['v'], ['w'], ['x'], ['y'], ['z']
 ];

 for (let i = 0; i < h.length; i++) {
   alphaArr[i].push(h[i])
 }
}

designerPdfViewer([1, 3, 1, 3, 1, 4, 1, 3, 2, 5, 5, 5, 5, 5, 5, 5, 5, 5, 5, 5, 5, 5, 5, 5, 5, 7], "zaba")
```
7:53 -- I think using the console.log() method is an excellent way to understand what your function is actually doing. Here's where I'm at now:
```
function designerPdfViewer(h, word) {
  let alphaArr = [
 ['a'], ['b'], ['c'], ['d'], ['e'],['f'], ['g'],
 ['h'], ['i'], ['j'], ['k'], ['l'], ['m'], ['n'], ['o'], ['p'], ['q'], ['r'], ['s'], ['t'], ['u'],
 ['v'], ['w'], ['x'], ['y'], ['z']
 ];

 for (let i = 0; i < h.length; i++) {
   alphaArr[i].push(h[i])
 }

 for (let i = 0; i < word.length; i++) {
   for (let ii = 0; ii < alphaArr.length; ii++) {

if (word[i] === alphaArr[ii][0]) {
     console.log("yes")
   }
   else {
     console.log(`our letter ${word[i]} alphaArr letter ${alphaArr[ii][0]}  `)
   }
   }
   
 }
}
```
7:59 -- I think I have a passable answer now...
```
function designerPdfViewer(h, word) {

  let tallestLetter = 0;
  let alphaArr = [
 ['a'], ['b'], ['c'], ['d'], ['e'],['f'], ['g'],
 ['h'], ['i'], ['j'], ['k'], ['l'], ['m'], ['n'], ['o'], ['p'], ['q'], ['r'], ['s'], ['t'], ['u'],
 ['v'], ['w'], ['x'], ['y'], ['z']
 ];

 for (let i = 0; i < h.length; i++) {
   alphaArr[i].push(h[i])
 }

 for (let i = 0; i < word.length; i++) {
   for (let ii = 0; ii < alphaArr.length; ii++) {

if (word[i] === alphaArr[ii][0]) {
     console.log("yes" + h[ii])
     if (h[ii] > tallestLetter) {
       tallestLetter = h[ii]
     }

   }
   else {
     console.log(`our letter ${word[i]} alphaArr letter ${alphaArr[ii][0]}  `)
   }
   }
   
 }
return (tallestLetter*word.length)
}
```
I'll try to clean things up a bit, submit it, and then explain it to you.

8:02 -- Solved! I'm going to take a break (only on 6 hours of sleep and haven't gone through morning routine yet).

When I come back I'll walk you through this algorithm.
___
8:56 -- I'm back. Let's break things down.

The first thing we have is a function *designerPdfViewer* which has two parameters *h*, and *word*.

*h* is an array whose items represent the height of each individual letter in the alphabet.

*word* represents a string of characters (letters in the intended use case).
```
function designerPdfViewer(h, word) {
}
```
9:00 -- Now, we need a couple variables. One is *tallestLetter* which we'll initialize to **0** and later use for storing the height of the tallest letter from the string passed to *word*.

We also need a variable *alphaArr* which is initialized to a 2-d array with each letter of the alphabet given its own sub-array.
```
function designerPdfViewer(h, word) {

  let tallestLetter = 0;
  let alphaArr = [
 ['a'], ['b'], ['c'], ['d'], ['e'],['f'], ['g'],
 ['h'], ['i'], ['j'], ['k'], ['l'], ['m'], ['n'], ['o'], ['p'], ['q'], ['r'], ['s'], ['t'], ['u'],
 ['v'], ['w'], ['x'], ['y'], ['z']
 ];
}
```
9:03 -- Of course, we're not finished yet. We need to loop through the array passed to *h* in order for us to assign said integers to the letters in our *alphaArr* (this will give each letter an appropriate height).
```
function designerPdfViewer(h, word) {

  let tallestLetter = 0;
  let alphaArr = [
 ['a'], ['b'], ['c'], ['d'], ['e'],['f'], ['g'],
 ['h'], ['i'], ['j'], ['k'], ['l'], ['m'], ['n'], ['o'], ['p'], ['q'], ['r'], ['s'], ['t'], ['u'],
 ['v'], ['w'], ['x'], ['y'], ['z']
 ];

 for (let i = 0; i < h.length; i++) {
   alphaArr[i].push(h[i])
 }
}
 ```
 9:06 -- Now that each letter in our *alphaArr* has been assigned a height, we now need to loop through each character in the string passed to *word*.

 We'll also nest another for loop inside our first for loop. The second for loop is for looping through each item in our *alphaArr*.

When our letter from *word* is equivalent to the letter from our *alphaArr*, we'll then evaluate if said letter is taller than the previous letter (value) assigned to *tallestLetter*.

If so, we'll assign *tallestLetter* the value of *h[ii]* (the current index and thus current height of a letter from our *h* array).

Otherwise, we'll simply continue looping through the rest of the characters in our *word* string.

Once we've finished looping through everything, we'll return the value assigned to *tallestLetter* times the length of the string passed to *word* for our solution to the algorithm.

*Why do we need to use multiplication?* Because our selection rectangle, like all rectangles has both a height (*tallestLetter*) and a width (*word.length*).

```
function designerPdfViewer(h, word) {

  let tallestLetter = 0;
  let alphaArr = [
 ['a'], ['b'], ['c'], ['d'], ['e'],['f'], ['g'],
 ['h'], ['i'], ['j'], ['k'], ['l'], ['m'], ['n'], ['o'], ['p'], ['q'], ['r'], ['s'], ['t'], ['u'],
 ['v'], ['w'], ['x'], ['y'], ['z']
 ];

 for (let i = 0; i < h.length; i++) {
   alphaArr[i].push(h[i])
 }

 for (let i = 0; i < word.length; i++) {
   for (let ii = 0; ii < alphaArr.length; ii++) {

if (word[i] === alphaArr[ii][0]) {
     if (h[ii] > tallestLetter) {
       tallestLetter = h[ii]
     }
      }
   }
   
 }
return (tallestLetter*word.length)
}
```
Aaaaaand we're done!

9:23 -- I'm feeling a bit sleepy (woke up early to code, only slept 6 hours). I'm going to take a break now and either sleep or get some exercise. In any case, I'm really glad to have already gotten over an hour of coding in today!

9:27 -- I currently have 196 points on HackerRank which is good enough for a global rank of 388,896. When I come back later today, I'm going to tackle an algorithm called [The Hurdle Race](https://www.hackerrank.com/challenges/the-hurdle-race/problem).
___
**Total time spent coding today**: 

**Total time spent coding thus far in June 2019**: 

**Total lifetime hours of coding**: 