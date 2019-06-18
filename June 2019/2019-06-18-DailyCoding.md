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

28:02 -- Solved! I'm going to take a break (only on 6 hours of sleep and haven't gone through morning routine yet).

When I come back I'll walk you through this algorithm.


___
**Total time spent coding today**: 

**Total time spent coding thus far in June 2019**: 

**Total lifetime hours of coding**: 