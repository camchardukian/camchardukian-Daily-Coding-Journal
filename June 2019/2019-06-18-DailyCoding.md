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
13:02 -- I guess I really was tired. I just woke up from a 3 hour nap! O_O 

13:03 -- Let's try to understand what we're working with for this algorithm...

13:05 -- This algorithm seems pretty simple. We've got a boy named Dan. He's playing a video game. Dan's character can jump a certain height which is represented by a variable *k* that is passed an integer.

We also have another parameter *height* which is passed an array of integers that represent how tall each individual hurdle Dan's character is required to jump over.

Finally, we have a magic potion that Dan's character can take which would increase how high he could jump by 1 unit.

Our job is to figure out the minimum numbers of doses (if any) Dan's character needs to take in order to jump over all of the hurdles (one at a time).

13:14 -- Just completed basic setup of the problem:
```
function hurdleRace(k, height) {
console.log(k, height)
}
```
13:17 -- Getting close...
```
function hurdleRace(k, height) {
  let tallestHurdle = 0;
for (let i = 0; i < height.length; i++) {
  if (tallestHurdle < height[i]) {
    tallestHurdle = height[i]
  }
}
return tallestHurdle
}
```
13:21 -- Wow, we're already finished! Here's my final solution:
```
function hurdleRace(k, height) {
  let tallestHurdle = 0;
  let potionsNeeded = 0;
for (let i = 0; i < height.length; i++) {
  if (tallestHurdle < height[i]) {
    tallestHurdle = height[i]
  }
}
if (tallestHurdle > k) {
  potionsNeeded = tallestHurdle - k
}
return potionsNeeded
}
```
13:22 -- Let's walk through it. First, we have a function *hurdleRace* which has two parameters *k* (an integer representing how high Dan's character can jump), and *height* (an array of integers representing the height of each individual hurdle Dan must jump over).

I've also defined a couple additional variables. *tallestHurdle* and *potionsNeeded*, both of which are initialized to 0.
```
function hurdleRace(k, height) {
  let tallestHurdle = 0;
  let potionsNeeded = 0;
}
```
The next thing we need to do is figure out which hurdle is tallest. We can do that by looping through our *height* array and seeing if each item's value is larger than the value which *tallestHurdle* is currently set to.
```
function hurdleRace(k, height) {
  let tallestHurdle = 0;
  let potionsNeeded = 0;
for (let i = 0; i < height.length; i++) {
  if (tallestHurdle < height[i]) {
    tallestHurdle = height[i]
  }
}
}
```
Finally, we can compare the values of *tallestHurdle* and *k* (which is the maximum height Dan can jump without potions).

If *tallestHurdle* is greater than *k* the height Dan can jump, we subtract *k* the height Dan can jump from our *tallestHurdle* variable and set our *potionsNeeded* variable equal to this integer.

Finally, we return our *potionsNeeded* variable as our solution to this algorithm.

Of course, if *tallestHurdle* was not greater than *k*, we would've simply broken out of our if statement, and returned potionsNeeded as the value it was initialized to (**0**).
```
function hurdleRace(k, height) {
  let tallestHurdle = 0;
  let potionsNeeded = 0;
for (let i = 0; i < height.length; i++) {
  if (tallestHurdle < height[i]) {
    tallestHurdle = height[i]
  }
}
if (tallestHurdle > k) {
  potionsNeeded = tallestHurdle - k
}
return potionsNeeded
}
```
We're finished!

13:41 -- I just finished commiting The Hurdle Race algorithm solution to my [HackerRank GitHub repo](https://github.com/camchardukian/hackerrank-algorithms).

13:42 -- I now have 211 points on HackerRank which is good enough for a global rank of 365,040. In my next coding session I'm going to work on the [Electronics Shop algorithm](https://www.hackerrank.com/challenges/electronics-shop/problem).
___

15:03 -- Just got back from almost an hour of exercising. Let's start working on the next algorithm.

15:05 -- It looks like in this problem we're dealing with a girl named Monica who is either a shopaholic or someone who is short on cash, but has an expiring gift card at a store.

Monica wants to buy both a keyboard and a USB drive. The store has a number of keyboards and USB drives at different price points.

Monica's goal is to buy exactly one keyboard, and one USB drive while spending as much money as possible in the process.

We need to print an integer representing the maximum amount of money Monica can spend while buying exactly one keyboard and one USB drive.

If Monica cannot afford both a keyboard and a USB drive, we'll simply print *-1*.

15:17 -- Basic function setup...
```
function getMoneySpent(keyboards, drives, b) {

console.log(`Monica's budget is ${b} the different keyboards cost ${keyboards} and the USB drives cost ${drives}`)

}
```
15:24 -- We're nearing the promise land...
```
function getMoneySpent(keyboards, drives, b) {
let mostExpensiveCombo = 0;

for (let i = 0; i < keyboards.length; i++) {

for (let ii = 0; ii < drives.length; ii++) {
  console.log(`i is ${keyboards[i]} and ii is ${drives[ii]}`)
}

}

}
```
15:33 -- I finished! Here's my final solution:
```
function getMoneySpent(keyboards, drives, b) {
let mostExpensiveCombo = 0;

for (let i = 0; i < keyboards.length; i++) {

for (let ii = 0; ii < drives.length; ii++) {
  if(keyboards[i] + drives[ii] > mostExpensiveCombo && keyboards[i] + drives[ii] <= b) {
    mostExpensiveCombo = keyboards[i] + drives[ii]
  } 
}
}
return (mostExpensiveCombo > 0 ? mostExpensiveCombo : -1)
}
```
15:34 -- Let's break things down. First, we define a function *getMoneySpent* which has three parameters *keyboards*, *drives*, and *b*.

*keyboards* and *drives* have arrays passed to them that represent respectively the costs of the stores' various keyboards and USB drives.

*b* represents Monica's budget.

I've also defined a new variable *mostExpensiveCombo* which is an integer representing the costliest combination of keyboards and USB drives Monica could purchase.
```
function getMoneySpent(keyboards, drives, b) {
let mostExpensiveCombo = 0;
}
```
15:40 -- Now, the first thing we need to do is loop through all of the different keyboards. As we go through each item in the *keyboards* array, we'll use a nested for loop to also go through all of the items in the *drives* array.

The reason we're doing this is to evaluate every possible combination of keyboards and USB drives.
```
function getMoneySpent(keyboards, drives, b) {
let mostExpensiveCombo = 0;

for (let i = 0; i < keyboards.length; i++) {

for (let ii = 0; ii < drives.length; ii++) {
}
}
}
```
15:43 -- Of course, we also need to add some logic. Our logic is as follows... If the cost of the given keyboard and USB drive is greater than the current value of *mostExpensiveCombo*, AND less than or equal to Monica's budget *b*, we will set the value of *mostExpensiveCombo* equal to the sum cost of the keyboard and USB drive we are currently looking at.

After going through every possible combination, we will then break out of our loops and utilize a return statement.

That return statement utilizes a ternary operator with the following logic:
> If the value of *mostExpensiveCombo* is greater than 0, it means Monica is capable of buying both a keyboard and a USB drive and we can return the value of *mostExpensiveCombo*. If not, it means Monica's budget wasn't large enough to purchase both a keyboard and a USB drive and we will instead return -1 as requested in this algorithm's explanation.

```
function getMoneySpent(keyboards, drives, b) {
let mostExpensiveCombo = 0;

for (let i = 0; i < keyboards.length; i++) {

for (let ii = 0; ii < drives.length; ii++) {
  if(keyboards[i] + drives[ii] > mostExpensiveCombo && keyboards[i] + drives[ii] <= b) {
    mostExpensiveCombo = keyboards[i] + drives[ii]
  } 
}
}
return (mostExpensiveCombo > 0 ? mostExpensiveCombo : -1)
}
```
We're finished!

15:58 -- I'm soooo hungry, but I guess I'll just use that as motivation (I've made a rule that I'm not allowed to eat until I've spent 4 hours doing deeply focused development work each day) to hustle.

15:59 -- In my next coding session I'll work on the [Utopian Tree algorithm](https://www.hackerrank.com/challenges/utopian-tree/problem).
___
**Total time spent coding today**: 

**Total time spent coding thus far in June 2019**: 

**Total lifetime hours of coding**: 