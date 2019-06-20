# Thursday June 20th, 2019 Daily Coding Journal

8:53 -- Yesterday was awesome. We got a ton of development practice. Let's see if we can replicate our strong efforts again today!

8:54 -- We're going to start off with me explaining my solution to the Minimum Distances algorithm from yesterday.

8:58 -- Here's my solution from yesterday:
```
function minimumDistances(a) {
let pairsArray = [];
let minimumDistance = Infinity;
let result;

for (let i = 0; i < a.length; i++) {
  for (let ii = i+1; [ii] < a.length+1 ; ii++) {
    if (a[i] === a[ii]) {
      pairsArray.push([i, ii])
    }
  }
}
if (pairsArray) {
for (let i = 0; i < pairsArray.length; i++) {
  if ((pairsArray[i][1]) - pairsArray[i][0] < minimumDistance) {
    minimumDistance = pairsArray[i][1] - pairsArray[i][0]
  }
}
}
minimumDistance < Infinity ? result = minimumDistance : result = -1

return result
}
```
8:59 -- Let's talk about how we got there.

9:00 -- First, we have a function *minimumDistances* that has a single parameter *a* which takes in an array of integers. Our goal is to find the minimum distance between any pair of matching integers (5 & 5 or 19 & 19 for example) our array may have. 

If there are multiple pairs, we'll find the distance for all of them and return the shortest possible distance between any of the pairs.

If there are no pairs of matching integers, we'll simply return -1. Here's our basic setup.

```
function minimumDistances(a) {

}
```
9:03 -- I've also defined a few additional variables: *pairsArray*: initialized to an empty array, *minimumDistance*: initialized to **Infinity**, and *result*: which is declared but not initialized to anything.
```
function minimumDistances(a) {
let pairsArray = [];
let minimumDistance = Infinity;
let result;
}
```
9:07 -- Next, we use a for loop to iterate through each item in the array passed to *a*. We also use a nested for loop to compare each item in our array to every other item in our array.

Plus, within our nested for loop we have an if statement wherein if we detect two matching integers (a[i] === a[ii]), we'll then push the position of those integers to *pairsArray*.

It's important to note that we're only pushing the position of said integers to *pairsArray*, and NOT the integers themselves. This is because this algorithm is interested in finding the distance between matching pairs, but gives no importance to how large or small those matching pairs may be.
```
function minimumDistances(a) {
let pairsArray = [];
let minimumDistance = Infinity;
let result;

for (let i = 0; i < a.length; i++) {
  for (let ii = i+1; [ii] < a.length+1 ; ii++) {
    if (a[i] === a[ii]) {
      pairsArray.push([i, ii])
    }
  }
 }
}
```
9:13 -- Eventually, we'll break out of our two for loops. When that occurs we have another if statement. This if statement basically says, if there is anything in our *pairsArray* do the following logic...

Said logic is a for loop which iterates through each item in *pairsArray*. Then, we ask ourselves:
> If a given item in our array's 1st value minus its "0th" value is less than the current value of *minimumDistance*, we'll then update the value of *minimumDistance* to equal the result of pairsArray[i][1] - pairsArray[i][0].

We'll loop through each item in *pairsArray* using that logic, updating *minimumDistance* as needed before eventually breaking out of our loop.

After doing so we have a ternary operator that says, if minimumDistance is less than **Infinity** (meaning, we must have updated *minimumDistance* at some point and thus our array obviously has some presence of matching integer pairs), we'll set our variable *result* equal to *minimumDistance*.

Otherwise, we'll set *result* equal to -1 (because our array didn't have any matching pairs of integers).

Finally, we'll return *result* as our solution to this algorithm!
```
function minimumDistances(a) {
let pairsArray = [];
let minimumDistance = Infinity;
let result;

for (let i = 0; i < a.length; i++) {
  for (let ii = i+1; [ii] < a.length+1 ; ii++) {
    if (a[i] === a[ii]) {
      pairsArray.push([i, ii])
    }
  }
}
if (pairsArray) {
for (let i = 0; i < pairsArray.length; i++) {
  if ((pairsArray[i][1]) - pairsArray[i][0] < minimumDistance) {
    minimumDistance = pairsArray[i][1] - pairsArray[i][0]
  }
}
}
minimumDistance < Infinity ? result = minimumDistance : result = -1

return result
}
```
Way to go!

9:30 -- I now have 411 points which gives me a global rank of 200,466 on HackerRank for algorithms and data structures.

9:31 -- During my next coding session I'll solve the [Drawing Book](https://www.hackerrank.com/challenges/drawing-book/problem) algorithm.
___
10:37 -- Here we go. 2nd coding session of the day.

10:38 -- We have a girl named Brie. Brie has to follow her teacher's direction to open her book to page *p*. Given that the book is *n* pages long, we must determine the minimum number of pages Brie must turn to arrive at *p*.

Here's the catch. Brie can start turning pages from either the front or the back of the book.

10:42 -- I'm going to try to solve this algorithm, while documenting my progress along the way. After I've found a solution, I'll share it with you here and explain how I came to it.

10:44 -- Basic function setup:
```
function pageCount(n, p) {

}
```
10:49 -- Figured out how many page turns from front to back. Now I think I can create a similar for loop to calculate page turns from back to front. Then, I can write a ternary statement to compare the two counts and set my variable *result* to the lesser of the two.
```
function pageCount(n, p) {
let frontToBack = 0;
let backToFront = 0;
let result;
for (let i = 1; i < p; i+=2) {
  frontToBack+=1
}
console.log(frontToBack)
}
```
11:01 -- Getting very close. Passed 26 out of 27 test cases:
```
function pageCount(n, p) {
let frontToBack = 0;
let backToFront = 0;
let result;
for (let i = 1; i < p; i+=2) {
  frontToBack+=1
}
for (let i = n - 1; i > p; i-=2) {
  backToFront+=1
}
frontToBack > backToFront? result = backToFront : result = frontToBack;

return result
}
```
11:30 -- I'm stuck. I'm going to take a break to try to clear my head.


___
**Total time spent coding today**: 

**Total time spent coding thus far in June 2019**: 

**Total lifetime hours of coding**: 