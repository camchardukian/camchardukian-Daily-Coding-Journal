# Friday June 21st, 2019 Daily Coding Journal

13:41 -- Here we go. I've gotten about 2.5 hours of productive work in thus far (on non-code related projects). I said that I was going to aim for 6 hours of productive work today.

Thus, that means I need to spend at least 3.5 hours coding. Uh-oh. We better get started!

13:44 -- We're working on the CamelCase algorithm on HackerRank. For this problem, it looks like we have a sequence of words in CamelCase. Our job is given the string *s*, determine how many words are in the string.

13:48 -- I think that for this problem, I may just be able to loop through the string, incrementing a variable *counter* for everytime *s[i]* === s[i].toUpperCase().

13:55 -- Wow, my initial brainstorm was the exact solution to the algorithm! Here's my solution:
```
function camelcase(s) {
    let counter = 1;
    for (let i = 0; i < s.length; i++) {
        if (s[i].toUpperCase() === s[i]) {
            counter += 1
        }
    }
    return counter
}
```
13:56 -- This algorithm is pretty simple. We have a function *camelcase* which has a single parameter *s*, which takes in a string of multiple words "mashed" together in CamelCase fashion.

Our job is given *s*, to determine how many words are in our string *s*.

Here's our basic function setup:
```
function camelcase(s) {

}
```
13:58 -- My logic in solving this problem was pretty simple. While the initial word begins with a lowercase letter, all of the succeeding words in our string *s* will begin with capital letters.

For that reason, my thinking was that we should create a variable *counter* and initialize said variable to 1.

*Why 1?* Because any given string passed to *s* will always have its first word begin with a lower case letter. By initializing *counter* to 1, we are accounting for this fact.

Moving forward, we're going to create a loop that iterates through every character in our string *s*. Any time we encounter a capital letter, we know that a new word has begun, and thus we should increment *counter* by 1.

In other words:
```
if (s[i].toUpperCase() === s[i]) {
    counter+=1
  }
```
After we've finished iterating through every character in our string *s*, we can return our variable *counter* as our solution to this algorithm!

Here's my finished solution I submitted successfully to HackerRank:
```
function camelcase(s) {
  let counter = 1;
for (let i = 0; i < s.length; i++) {
  if (s[i].toUpperCase() === s[i]) {
    counter+=1
  }
}
return counter
}
```
Thanks for following along. I hope you found my instructions useful! :D

14:12 -- Wow, we solved that last algorithm *FAST*.

14:13 -- During my next coding session, I'll try to solve the Diagonal Difference algorithm that left me frustrated a couple weeks ago. Maybe it'll be easy now with my increased familiarity with HackerRank and algorithm solving :))

14:14 -- In any case, I now have 501 points which is good enough for a rank of 164,532 on HackerRank's global algorithm leaderboard.
___
14:37 -- Just got back from a quick break talking with my parents and walking around the house to get the blood flowing. Now, let's try to solve that Diagonal Difference algorithm once and for all!

14:40 -- Just spent the last few minutes making some sketches to remember exactly what this algorithm was asking. Now, I'll try to write some code and see if I can solve it.

14:45 -- Basic setup:
```
function diagonalDifference(arr) {
let primary = 0
let secondary = 0;

for (let i = 0; i < arr.length; i++) {
  console.log(arr[i])
 }
}
```
14:54 -- Still working...
```
function diagonalDifference(arr) {
let primary = 0
let secondary = 0;
let squareRoot = Math.sqrt(arr.length)
for (let i = 0; i < arr.length; i+=(squareRoot+1)) {
  primary+=arr[i]
 }

 for (let i = squareRoot-1; i < arr.length -1; i+=(squareRoot-1)) {
secondary+=arr[i]
 }
 console.log(`primary is ${primary} and secondary is ${secondary}`)
}
```
15:01 -- My solution appears to work in repl.it, but things are buggy thus far on HackerRank:
```
function diagonalDifference(arr) {
let primary = 0
let secondary = 0;
let squareRoot = Math.sqrt(arr.length)
for (let i = 0; i < arr.length; i+=(squareRoot+1)) {
  primary+=arr[i]
 }

 for (let i = squareRoot-1; i < arr.length -1; i+=(squareRoot-1)) {
secondary+=arr[i]
 }

 return Math.abs(primary-secondary)
}
```
15:19 -- *Sigh* it looks like where I've been going wrong is that this problem says that function *diagonalDifference* has a parameter *arr* which takes in an array of integers, but this "array" is actually a 2-d array.

15:21 -- Back to the drawing board, it's like we're basically having to go solve a whole different algorithm.

15:32 -- I'm so over this problem. On my own I created a working solution:
```
function diagonalDifference(arr) {
let primary = 0;
let secondary = 0;
let result;
for (let i = 0; i < arr.length; i++) {
  primary+=arr[i][i]
}
for (let i = 0; i < arr.length; i++) {
  secondary+= arr[i][arr.length-i-1]
}
return Math.abs(primary-secondary)
}
```
I must have failed too many times along the way, however, because depite successfully passing all of this problem's user tests and having a 10 points submission, no points actually got credited to my account.

15:34 -- I need to take a break. I'm about to go Hulk rage mode lol.
___
15:57 -- Let's talk about the Diagonal Differences algorithm.

15:58 -- We have a function *diagonalDifference* that has a parameter *arr*. LISTEN UP. Though the problem orientation page states that *arr* is an array of integers, it's important to note that *arr* is actually a 2-d array of integers.

I wasted several hours trying to solve this problem, having my solution work perfectly on repl.it, but having it fail on HackerRank countless times.

Eventually after playing around with the user tests on HackerRank, I realized that they gave us a 2-d array, and not a standard array of integers.

With that being said, here's our basic function setup:
```
function diagonalDifference(arr) {

}
```
16:01 -- Next, I've also defined a few additional variables: *primary* and *secondary* initialized to **0**, and a variable *result* declared but not given any initial value.
```
function diagonalDifference(arr) {
let primary = 0;
let secondary = 0;
let result;
}
```
16:04 -- Now that we've got our function setup and declared all of our variables, we're going to create a for loop. Our first for loop will be used to increment *primary* by the values that make up a line drawn through the primary diagonal of any square of integers.

Our second for loop increments *secondary* by the values that make up a line drawn through the secondary diagonal of any square of integers.
```
function diagonalDifference(arr) {
let primary = 0;
let secondary = 0;
let result;
for (let i = 0; i < arr.length; i++) {
  primary+=arr[i][i]
}
for (let i = 0; i < arr.length; i++) {
  secondary+= arr[i][arr.length-i-1]
}
```
16:08 -- Now that the sum of all of our values in the two diagonal lines drawn through a square are stored in either *primary* or *secondary*, we can then return the absolute value of *primary* minus *secondary* as our solution to this algorithm!
```
function diagonalDifference(arr) {
let primary = 0;
let secondary = 0;
let result;
for (let i = 0; i < arr.length; i++) {
  primary+=arr[i][i]
}
for (let i = 0; i < arr.length; i++) {
  secondary+= arr[i][arr.length-i-1]
}
return Math.abs(primary-secondary)
}
```
16:10 -- If you found this algorithm frustrating or confusing, you're not alone.

This may be my first month solving algorithms on HackerRank (June 2019), but of the 30+ algorithms I've solved thus far, this is the only algorithm that made me so frustrated I had to store it away for a couple weeks before coming back to it.

In retrospect, this algorithm wouldn't have been so frustrating if the instructions were written more clearly, or... taking personal responsibility -- I could have maintained my composure and solved this algorithm more quickly by ensuring I'd understood what the author was looking for, even if their explanation was unclear to me and my only real way of understanding the problem was playing with the console and various user tests.

At the very least, I've learned a lesson and if in the future my code isn't working the way I expect, I'll go straight to the user tests and play with the console to see if the inputs my function is receiving are in a different format than I expected.

16:19 -- The high of my week is probably finally finishing that 'Diagonal Difference' algorithm lol.

16:21 -- It looks a little bit challenging, but during my next coding session I'll try to solve the 'Equalize the Array' algorithm.
___
18:44 -- Ate a few apples and took a long late afternoon nap. Now it's time to work.

18:47 -- For this problem, we have an array, and we need to count the minimum number of deletions it would take for us to modify our array to contain items of only a single value. In other words, we'd like to go from:
> [0, 2, 4, 4, 5] --> [4, 4]

I'm wondering if all we need to do, is simply find the number in the array that occurs most often, and simply take the length of our array minus the number of times our most frequently appearing item occured...

16:56 -- Some progress...
```
function equalizeArray(arr) {
let currentFrequency = 0;
let greatestFrequency = [0, 0];

for (let i = 0; i < arr.length; i++) {
  for (let ii = i + 1; ii < arr.length; ii++) {
    console.log()
  }
 }
}
```
19:06 -- Still chugging along:
```
function equalizeArray(arr) {
let currentFrequency = 1;
let mostFrequentNumber;
let highestOccurenceCount = 1;

for (let i = 0; i < arr.length; i++) {
  currentFrequency = 1
  for (let ii = i + 1; ii < arr.length; ii++) {
    console.log(`arr[i] is: ${arr[i]} and arr[ii] is: ${arr[ii]}`)
    if (arr[i] === arr[ii]) {
      currentFrequency+=1
    }
  }
  if (currentFrequency > highestOccurenceCount) {
    highestOccurenceCount = currentFrequency;
    mostFrequentNumber = arr[i]
  }
}
  console.log(`most frequent number is ${mostFrequentNumber} and highest occurence count is ${highestOccurenceCount}`)
}
```
19:09 -- I solved the algorithm! Here's my final solution:
```
function equalizeArray(arr) {
let currentFrequency = 1;
let highestOccurenceCount = 1;

for (let i = 0; i < arr.length - 1; i++) {
  currentFrequency = 1
  for (let ii = i + 1; ii < arr.length; ii++) {
    if (arr[i] === arr[ii]) {
      currentFrequency+=1
    }
  }
  if (currentFrequency > highestOccurenceCount) {
    highestOccurenceCount = currentFrequency;
  }
}
  return (arr.length - highestOccurenceCount)
}
```
19:10 -- I'm feeling a bit mentally drained right now. I'm going to go eat dinner (or just make a green smoothie haha), and then I'll explain this algorithm's solution when I return.
___
20:35 -- Just downed a green smoothie and spent an hour chatting with my mom and pacing the living room.

20:36 -- Let's discuss our solution. We have a function *equalizeArray* which has a single parameter *arr* which takes in an array of integers.

I've also created two variables: *currentFrequency*, and *highestOccurenceCount*, both initialized with a value of 1.

Here's our basic setup:
```
function equalizeArray(arr) {
let currentFrequency = 1;
let highestOccurenceCount = 1;
 }
```
20:40 -- Next, we're going to use a for loop to iterate through all of the items in our array. We're also going to update the value of *currentFrequency* to 1.

This is because we're later going to modify the value of *currentFrequency* in our upcoming nested for loop. But... we want the value of *currentFrequency* to equal 1 before we enter our nested for loop each time.

Thus, we need to update the value of *currentFrequency* to 1 with each iteration of our outer for loop:
```
function equalizeArray(arr) {
let currentFrequency = 1;
let highestOccurenceCount = 1;

for (let i = 0; i < arr.length - 1; i++) {
  currentFrequency = 1
 }
}
```
20:45 -- As I mentioned earlier, we're now going to need a nested for loop. The role of this inner for loop is to count how many times a particular item occurs within our array.

Each time an item occurs, we'll increment the value of *currentFrequency* by one. 

After we eventually break out of our nested for loop, we'll then reach an if statement. This if statement says that if *currentFrequency* or the number of times our current item has occured, if that is greater than *highestOccurenceCount* or the greatest number of times any single item (excluding the current item) thus far has occured, we'll then set the value of *highestOccurenceCount* to the value of *currentFrequency*.
```
function equalizeArray(arr) {
let currentFrequency = 1;
let highestOccurenceCount = 1;

for (let i = 0; i < arr.length - 1; i++) {
  currentFrequency = 1
  for (let ii = i + 1; ii < arr.length; ii++) {
    if (arr[i] === arr[ii]) {
      currentFrequency+=1
    }
  }
  if (currentFrequency > highestOccurenceCount) {
    highestOccurenceCount = currentFrequency;
  }
}
```
20:51 -- We'll continually run through both of our loops as long as *i* is less than arr.length - 1. When that stops being the case, however, we'll break out of our outer for loop and return (arr.length - highestOccurenceCount) as our solution to this algorithm!

The reasoning behind this logic, is that if we have some list of numbers and we want to make deletions until all of the numbers are the same, we know that the only number we won't be deleting is the number that occured most often.

For example:
> [0, 1, 1, 2]

In the above array of numbers, we have 4 numbers. Or in other words, our array's length has a value of 4.

In this array, our most frequently occuring number is 1. This number occurs two times. We know that we won't be deleting the ones from our array, because they are value that occurs most frequently.

We do know, however, that we will be deleting every other item in our array. Thus, if we take the number of items in our array (4 items), minus the number of times our most frequently item occurs (1 occurs two times), that will equal the number of deletions we must perform in order to have a new array that consists of only our most frequently occuring value!

Here's our final solution to this algorithm:
```
function equalizeArray(arr) {
let currentFrequency = 1;
let highestOccurenceCount = 1;

for (let i = 0; i < arr.length - 1; i++) {
  currentFrequency = 1
  for (let ii = i + 1; ii < arr.length; ii++) {
    if (arr[i] === arr[ii]) {
      currentFrequency+=1
    }
   }
  if (currentFrequency > highestOccurenceCount) {
    highestOccurenceCount = currentFrequency;
  }
 } 
  return (arr.length - highestOccurenceCount)
}
```
I hope my explanation of our solution made sense to you. If you're having a difficult time catching on, don't worry.

A moderate amount of discomfort experienced while programming, a feeling that you're being stretched... doesn't mean your stupid. It just means you're learning.

Keep putting the time in everyday, and gradually over time things will begin to "click" more and more quickly! :D

21:07 -- Finished commiting that last algorithm solution to GitHub.

21:08 -- I now have 521 points, which is good enough for a rank of 157,572 on HackerRank's global algorithm leaderboard.

21:09 -- During my next coding session, I'll solve the Kangaroo algorithm.
___
23:35 -- I'm back. Just ate a few apples, got a haircut, and spent some time talking with my dad. Now it's time for 25+ minutes of coding so that we can hit 6+ hours of productive work today.

23:36 -- I'm working on the [Kangaroo](https://www.hackerrank.com/challenges/kangaroo/problem) algorithm on HackerRank.

23:37 -- It looks like we have two kangaroos, and our job is to determine will the two kangaroos ever land in the same position after taking the same number of jumps.

23:39 -- Logically, my initial thought is that we can take the kangaroo with a larger jump distance, and when that kangaroo is further along, we know to terminate our loop and print "NO" (because if one kangaroo is already behind AND it's slower, it will never catch up).

If the "fast" kangaroo, and the "slow" kangaroo are ever in the same position, however, we can check if they've taken the same number of jumps. If so, we'll print "YES" to the console.

If not, we'll print "NO".

So far, I've yet to identify a problem with my logic. But, I'll try to implement my solution now, and see if any issues come up.

23:46 -- Initial setup:
```
function kangaroo(x1, v1, x2, v2) {

}
```
23:57 -- Here's my current code:
```
function kangaroo(x1, v1, x2, v2) {
if (v1 > v2) {
  while (x1 < x2) {
    x1+= v1;
    x2+= v2;
    if (x1 === x2) {
    return "YES1"
    }
  }
}
  else if (v1 < v2) {
    while (x1 > x2) {
      x1+= v1;
      x2+= v2;
      if (x1 === x2) {
        return "YES2"
      }
    }
  }
  return "NO"
}
```
It passed 17/30 of the user tests. I couldn't figure out why it didn't pass all the tests. Then, I realized I forgot to change return "YES1" and "YES2" to a simple yes lol.

23:59 -- In any case, the algorithm is solved, and I'll see you in tomorrow's daily coding journal entry!
___
**Total time spent coding today**: 3 hours 39 minutes

**Total time spent coding thus far in June 2019**: 54 hours 51 minutes

**Total lifetime hours of coding**: 626 hours 34 minutes