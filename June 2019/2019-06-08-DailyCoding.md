# Saturday June 8th, 2019 Daily Coding Journal

14:58 -- Off to a bit of a late start today. No worries, let's get to working on the next algorithm.

15:01 -- I'm now working on the [Staircase](https://www.hackerrank.com/challenges/staircase/problem) algorithm on hackerrank.

15:02 -- This problem doesn't seem too difficult. Let's define what we need to do.

>1. Write a function that takes in a parameter *'n'*.
>1. Print our staircase based on the fact that the number passed as our 'n' argument represents the height and base of said staircase. 

15:07 -- Here's the basic setup I've gone through so far:
```
function staircase(n) {
console.log(n)
}
staircase(4);
```
15:11 -- I've spent a few more minutes working on this problem. Here's where I'm at now:
```
function staircase(n) {
for (let i = n; i > 0; i--){
  let current = '#';
  console.log(current);
}
}
staircase(4)
```
My function currently prints a hashtag('#') to the console every time my loop is run. Now, I think I may have to use a nested for loop to push a hashtag to my loop based on the current value of ('i').

15:24 -- Had to go backwards to go forward. Before, I was printing the staircase in the correct dimensions, but my usage of decrementing instead of incrementing resulted in the staircase being printed upside down.

Here's my new basic foundation:
```
function staircase(n) {
for (let i = 1; i <= n; i++){
    let current = [];
}
}
staircase(4)
```

15:39 -- Still here, just feeling kind of lost...

15:45 -- My current code is getting close. I just need to change the way I'm adding spaces to my staircase:
```
function staircase(n) {
for (let i = n+1; i > 0; i--){
    let current = [];
    for (let ii = i; ii <= n; ii++) {
      current.push('#')
    }
if (current.length > 1) {
    current = current.join(" ")
    console.log(current)
}
else {
  console.log(current.join(""))
}
    }

}
staircase(13)
```
___
16:11 -- I took a break. Now I'm back.

16:14 -- I'm trying to convert my staircase from being left-aligned to right-aligned.

16:20 -- Here's my thinking. I can take the value of n because that's how many hashtags there will be. Let's say n = 5. The first time through the loop I don't need to add any spaces. The next time I need to add one space, then two spaces, and so on. Basically, my pseudocode equation is this:
```
if (hashtag count + spaces added = n) {log string as is to the console}

else keep adding spaces until the above equation equals n.
```
16:43 -- I finally finished! Here's my final code output:
```
function staircase(n) {
for (let i = n+1; i > 0; i--){
    let current = [];
    for (let ii = i; ii <= n; ii++) {
      current.push('#');
    }
current = current.join("");
if (current.length <= n && current.length > 0) {
  if (current.length != n) {
    for (let j = current.length; j < n; j++) {
      current = ` ${current}`
    }
    console.log(current)
  }
  else {
    console.log(current)
  }
}
}
}
staircase(4)
```
16:44 -- Let's break things down so we can internalize the lessons we are supposed to learn.

16:46 -- First, we create a function that takes a parameter of 'n':
```
function staircase(n) {

    }
```
Then, we create a for loop that will run a set amount of times based upon the number passed to our staircase function. We also initialize our current variable to an empty array, and create a for loop that pushes a hashtag ("#") to our current array each time through the loop.
```
for (let i = n+1; i > 0; i--){
    let current = [];
    for (let ii = i; ii <= n; ii++) {
      current.push('#');
    }
```
After exiting our for loop that's in charge of pushing our hashtags to *current*, we then use the join() method on our *current* array to manipulate it into a string, and set our current variable to the result:
```
function staircase(n) {
for (let i = n+1; i > 0; i--){
    let current = [];
    for (let ii = i; ii <= n; ii++) {
      current.push('#');
    }
current = current.join("");
```
From there, we use the logic that if the length of our current string is less than the length of the number passed as an argument to our staircase function's 'n' parameter, we know that we need to add spaces.
*Why?*

Because if the length of our *current* string was equal to 'n', we'd know that spaces would be unnecessary because we'd be working with the base of the staircase:
```
function staircase(n) {
for (let i = n+1; i > 0; i--){
    let current = [];
    for (let ii = i; ii <= n; ii++) {
      current.push('#');
    }
current = current.join("");
if (current.length <= n && current.length > 0) {
  if (current.length != n) {
    for (let j = current.length; j < n; j++) {
      current = ` ${current}`
    }
    console.log(current)
  }
  else {
    console.log(current)
  }
}
}

}
staircase(4)
```
16:59 -- WOW! That was a lot of thinking. I'm feeling pretty tired now. I'm going to commit this journal entry to GitHub, commit the solution to my hackerrank repo, and then take a break.

___
**Total time spent coding today**: 1 hour 57 minutes

**Total time spent coding thus far in June 2019**: 18 hours 19 minutes

**Total lifetime hours of coding**: 589 hours 37 minutes