# Wednesday June 26th, 2019 Daily Coding Journal

0:05 -- I just finished commiting everything from yesterday to GitHub. Tomorrow morning, I'll work to solve the [Taum and B'day](https://www.hackerrank.com/challenges/taum-and-bday/problem) algorithm.

See you then!
___
9:13 -- I'm up. Let's knock out the Taum and B'day algorithm.

9:14 -- For this problem, it looks like we have a boy named Taum who needs to buy presents for his friend Diksha's birthday.

To make Diksha happy Taum has to buy her a certain number of white gifts *w*, and a certain number of black gifts *b*.

Taum wants to spend the minimum amount of money necessary to do so. The cost for black gifts is *bc*, the cost of white gifts is *wc*, and the cost of converting the gifts from one color to another is *z*.

Our job is to determine the minimum amount of money Taum needs to buy Diksha the gifts she wants.

Here's our basic function setup:
```
function taumBday(b, w, bc, wc, z) {

}
```
9:20 -- I'll document my progress as I go, and explain my final solution to you once I reach one.

9:27 -- Here's my pseudocode brainstorm:
```

// If we need to buy black gifts, determine whether bc < wc + z. If so, multiply bc * b. If not, multiply (wc + z) * b and set equationOneResult equal to the result.

// If we need to buy white gifts, determine whether wc < bc + z. If so, multiply wc * w. If not, multiply (bc + z) * b, and set equationTwoResult equal to result.

// Add equationOneResult plus equationTwoResult to get our solution to this algorithm!
```
9:33 -- Working to implement my pseudocode. Halfway there...
```
function taumBday(b, w, bc, wc, z) {
let equationOneResult;
let equationTwoResult;

if (b > 0) {
  if (bc <= wc + z) {
    equationOneResult = bc * b
  }
  else if (bc > wc + z) {
    equationOneResult = (wc + z) * b
  }
 }
}
```
9:35 -- Taking a 20 minute break to handle something, be back soon.

9:58 -- I'm back. Let's finish solving this algorithm.

10:08 -- I've almost solved the algorithm. I've passed 13/15 test cases. It looks like the only issue is that I need to deal with the small value discrepancies that sometimes occur in JavaScript as a result of the manner in which the language uses binaries in dealing with numbers.

10:19 -- Quite honestly, I'm feeling lost. My use of the Math.round() method has only resulted in decreased performance it seems.

My function now only passed 10/15 test cases:
```
function taumBday(b, w, bc, wc, z) {
let equationOneResult;
let equationTwoResult;

if (b > 0) {
  if (bc <= wc + z) {
    equationOneResult = Math.round((bc * b)*100000)/100000
  }
  else if (bc > wc + z) {
    equationOneResult = Math.round(((wc + z) * b)*100000)/100000
  }
  else {
    return ("Error: incorrect input")
  }
 }
 if (w > 0) {
   if (wc <= bc + z) {
     equationTwoResult =  Math.round((wc * w)*100000)/100000
   }
   else if (wc > bc + z) {
     equationTwoResult = Math.round(((bc + z) * w)*100000)/100000
   }
   else {
     return ("Error: incorrect input")
   }
 }
 return (Math.round(equationOneResult + equationTwoResult)*100000)/100000
}
```
10:41 -- To make a long story short, it seems the numbers in this problem were too large for JavaScript to handle.

As such, getting a perfect score on this algorithm requires the use of the BigNumber library.

Whenever I try to use the bignumber library I seem to get a runtime error with my solution:
```
function taumBday(b, w, bc, wc, z) {
let equationOneResult;
let equationTwoResult;

if (b > 0) {
  if (bc <= wc + z) {
    equationOneResult = bc * BigNumber(b)
  }
  else if (bc > wc + z) {
    equationOneResult = (wc + z) * BigNumber(b)
  }
  else {
    return ("Error: incorrect input")
  }
 }
 if (w > 0) {
   if (wc <= bc + z) {
     equationTwoResult =  wc * BigNumber(w)
   }
   else if (wc > bc + z) {
     equationTwoResult = (bc + z) * BigNumber(w)
   }
   else {
     return ("Error: incorrect input")
   }
 }
 return (BigNumber(equationOneResult) + BigNumber(equationTwoResult))
}
```
Not to leave you hanging, however, here's an example from the [community](https://www.hackerrank.com/challenges/taum-and-bday/forum) of a user that successfully used the library to earn a full 25 points whereas my original solution (without bignumber) was only enough to earn 19 points (because of native JavaScript's limitations in dealing with very large numbers).

Here you go:
```
const BigNumber = require('bignumber.js')

function taumBday (b, w, bc, wc, z) {
    [b, w, bc, wc, z] = [...arguments].map(x => new BigNumber(x))
    let tbc = BigNumber.min( b.times(bc), b.times(wc).plus(b.times(z)) )
    let twc = BigNumber.min( w.times(wc), w.times(bc).plus(w.times(z)) )
    return tbc.plus(twc).toFixed()
}
// courtesy of HackerRank user 
adamxtokyo
```
10:50 -- While this problem had some complexities, I hope you were able to get some value out of our discussion!

While my understanding of the BigNumber library is pretty sketchy, you can [read more about it here](https://github.com/MikeMcl/bignumber.js/).

11:03 -- Man that last problem was exhausting. That was the rare problem PHP would've outperformed JavaScript lol.

In any case, I'm glad it's finished.

I now have 666 points which is good enough for a rank of 119,836 on HackerRank's global algorithm leaderboard.

11:08 -- During my next coding session I'll attempt to solve HackerRank's [Library Fine algorithm](https://www.hackerrank.com/challenges/library-fine/problem).
___
18:11 -- Got some exercise in, did a few hours of work on a personal obligation, got a few hours of sleep in, and now we're here!

18:13 -- Let's start working on the algorithm!

18:14 -- It looks like we have a local library that wants us to build an application that calculates the fee (if any is applicable) to books that are returned after their expected return date.

We have a function *libraryFine* that has several parameters:
* *d1*, *m1*, *y1*: Integers representing the day, month, and year on which the book was returned.
* *d2*, *m2*, *y2*: Integers representing the day, month, and year on which the book was *supposed* to be returned by.

To see full details on how this algorithm wants us to calculate fines, please [see its page on HackerRank](https://www.hackerrank.com/challenges/library-fine/problem).

Otherwise, here are the basic elements to keep in mind:

1. If the book is returned on or before the expected return date, no fine will be charged (fine = 0)

1. If the book is returned after the expected return day but still within the same calendar month and year as the expected return date (fine = 15 Hackos x number of days late)

1. If the book is returned after the expected return month but still within the same calendar year as the expected return date, (fine = 500 Hackos x number of months late)

1. If the book is returned after the calendar year in which it was expected, there is a fixed fine of
(fine = 10000 Hackos)

18:24 -- I'm going to solve this problem, documenting my progress along the way. When I reach a final solution, we'll then go over everything together.

18:26 -- Basic problem setup:
```
function libraryFine(d1, m1, y1, d2, m2, y2) {

}
```
18:33 -- My function now knows to assess a fine of 10,000 if the book is returned at any point after the year in which it was due:
```
function libraryFine(d1, m1, y1, d2, m2, y2) {
let fine;

if (y1 > y2) {
  fine = 10000;
  return fine;
}
console.log("not yet able to calculate fine for said dates")
}
```
18:43 -- I did it! Here's my final working solution:
```
function libraryFine(d1, m1, y1, d2, m2, y2) {
let fine;

if (y1 > y2) {
  fine = 10000;
  return fine;
}
if (y1 === y2) {
if (m1 > m2) {
  fine = (m1-m2)*500
  return fine
    }

 else if (m1 === m2) {
  if (d1 > d2) {
    fine = (d1-d2)*15
    return fine
   }
  }
 }

fine = 0
return fine
}
```
18:44 -- The only thing that tripped me up for a minute about this problem was that I initially forgot to consider the possibility that our return date may be in the year prior to our due date.

Once I accounted for that possibility, however, everything was smooth sailing. I'll explain my solution to you during my next coding session!
___
**Total time spent coding today**: 

**Total time spent coding thus far in June 2019**: 

**Total lifetime hours of coding**: 