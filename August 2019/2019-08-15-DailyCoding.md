# Thursday August 15th, 2019 Daily Coding Journal

8:33 -- Yesterday I got my daily coding habit started up again. I didn't put in as much time as I would've liked, but at least I sat down and did something. 

I'm hoping to build upon yesterday, by going a little bit deeper into the programming processes today.

8:49 -- Here's some pseduocode I just put together:
```
// start calculating square roots from the bottom end of our range "a".

// if the square root of "a" is an integer, we'll know that is our first square integer and push it to our results array. We'll also update the value of current to equal the square root of a.

// If the square root of "a" is NOT an integer, we WON'T push the square root of A to our results array. We'll then update the value of "current" to equal Math.ceil the square root of "a".

// We'll then use a loop whose function will be to increment current by 1, and if "current" squared is less than "b", we'll push the value of "current" to our array "results", increment "current" by 1, and repeat the process for as long as "current" squared is less than "b".

// We can then take the length of our "results" array as our solution to this algorithm!
```

8:57 -- My pseudocode worked out exactly as planned! :D Here's my final solution:
```
function squares(a, b) {
  let result = [];
  let current;

  current = Math.sqrt(a);

  if (current > 0 && current == Math.floor(current)) {
    result.push(current)
    current+=1
  }
  else {
    current = Math.ceil(current);
  }

  for (let i = current; current*current <= b; current+=1) {
    result.push(current)
  }

  return (result.length)
}
```

During my next coding session I'll explain exactly why this solution works. For now, however, I'm just going to take a minute to appreciate the small victory of getting a coding session in early in the morning.

I haven't done that in a long time! It's great to always be hungry for more, but it's also important to appreciate the small successes along the way :)
___
18:27 -- I'm back. I just ordered dinner. Now, I'm going to explain my solution for the last algorithm before eating.

I'm a bit tired given that I'm only on 5.5 hours of sleep, but at least I woke up early today hahaha.

18:28 -- We have a function *squares* with two parameters: *a* and *b*. Our goal in using the *squares* function is to find all of the square numbers in a given range.

In this explanation, when I say square number, I'm referring to an integer (not floating point) received from taking the square root of one of the numbers in our range of numbers.

In our function, *a* is the beginning point of our range of numbers, and *b* is the ending point.

Here's our basic function setup:
```
function squares(a, b) {
}
```
18:38 -- Now that we've gotten our basic function setup, we need to define some variables. In my solution, I've defined a variable *current* and initialized it to the value of the square root of *a*.

*Why?* Because the smallest possible square number we could have is the square root of the first/smallest number in our range of numbers which would be *a*.

I've also defined a variable *result*, and initialized it to an empty array.

My thinking is that each time we encounter a square number from taking the square root of a number in our range, we can push the square number to our array *results*.

Of course, this algorithm is asking us for the quantity of square numbers in a range and NOT what those square numbers are themselves.

Thus, you could also initialize *result* to the number 0, or instead of naming your variable result you could instead name it *counter*, and simply increment *counter* each time you "found" a square number.

I chose not to do this because I thought there may be some circumstances in which a user may be curious what square numbers are within the range they have chosen.

This isn't explicitly defined, however, so both my interpretation and the alternate interpretation are perfectly valid.

In any case, here's where we are at now:
```
function squares(a, b) {
  let result = [];
  let current = Math.sqrt(a);
}
```
18:45 -- Next, we're going to use a quick if statement. If *current* is equal to Math.floor(current) we're going to push the value of *current* to our array *results*.

In other words, if the value of *current* equals the value of *current* rounded down to the nearest number (the purpose of using Math.floor()), we'll know that *current* is a whole number because no changes happened when it was rounded down to the nearest whole number.

Thus, we know we can push the value of *current* to our array *result*.

Otherwise/else if *current* does NOT equal Math.floor(current), we'll know that *current* is some floating point (decimal) number. Thus, we'll round *current* up the nearest whole number using Math.ceil().

*Why wouldn't we round current down in this scenario?* The answer is very simple. If the square root of our smallest number is some floating point, for example our range starts at 90 which has a square root of roughly 9.4848.

In this case, we know that the smallest possible square number (integer) that could be produced from our range of numbers would be 10 because even the smallest number in our range was greater than 9.
```
function squares(a, b) {
  let result = [];
  let current = Math.sqrt(a);

  if (current == Math.floor(current)) {
    result.push(current)
    current+=1
  }
  else {
    current = Math.ceil(current);
  }
}
```
18:55 -- Now that we've made is this far, the rest of our solution is pretty simple. We'll run a for loop that's initial value is set to *current*.

We'll then continue running our loop for as long as *current* times *current* is less than or equal to the greatest number in our range *b*.

Each time we run our loop, we'll increment the value of *current* by 1.

With each iteration of our loop, we'll push the value of *current* to our array *result*.

The reason this works is because the reverse of taking the square root of a number is multiplying a number by itself (or in mathematical terms... squaring a number).

If the value of *current* multipled by itself (current) equals a number that is less than the greatest number in our range, we can conclude that *current* is a square number!
```
function squares(a, b) {
  let result = [];
  let current = Math.sqrt(a);

  if (current == Math.floor(current)) {
    result.push(current)
    current+=1
  }
  else {
    current = Math.ceil(current);
  }

  for (let i = current; current*current <= b; current+=1) {
    result.push(current)
  }
}
```
19:01 -- We've now pushed all of the square numbers to our array *result*. However, it's important that this algorithm doesn't care about the contents of our array.

The algorithm is simply asking how many items are in our array (in other words... how many square numbers we're produced from taking the square root of the numbers in the range *a* to *b*).

Thus, to "count" the number of items in our array and produce a final solution, we can return *result.length* as our solution to this algorithm!
```
function squares(a, b) {
  let result = [];
  let current = Math.sqrt(a);

  if (current == Math.floor(current)) {
    result.push(current)
    current+=1
  }
  else {
    current = Math.ceil(current);
  }

  for (let i = current; current*current <= b; current+=1) {
    result.push(current)
  }

  return (result.length)
}
```
19:09 -- I now have 902.92 points which is good enough for a rank of 85,757 on HackerRank.

19:12 -- During my next coding session, I'll try to solve the [Between Two Sets algorithm](https://www.hackerrank.com/challenges/between-two-sets/problem).

22:48 -- UPDATE: I'll get to solve that algorithm tomorrow. For now, I'm going to do a little bit more work on other projects before getting an early night of sleep (at least early compared to the usual times I've been going to bed lately.)
___
**Total time spent coding today**: 1 hour 24 minutes

**Total time spent coding thus far in August 2019**: 3 hours 17 minutes

**Total lifetime hours of coding**: 682 hours 57 minutes