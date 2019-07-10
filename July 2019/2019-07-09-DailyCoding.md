# Tuesday July 9th, 2019 Daily Coding Journal
19:08 -- I'm feeling pretty tired. My sleep schedule is going against the sun, but I haven't changed it because I'm getting ready to go back to Vietnam tomorrow.

In any case, I'm going to try to get in a quick 20 minute coding session before dinner. Here we go!

19:09 -- I'm working on The [Love-Letter Mystery](https://www.hackerrank.com/challenges/the-love-letter-mystery/problem) algorithm on HackerRank.

19:10 -- For this problem, it looks like we have a boy named James that discoverd a love letter that his friend Harry wrote to his girlfriend.

James changes the letters around so that each word becomes a palindrome. A palindrome is basically a word that is spelled the same both forwards and backwards.

Our job is to determine how many "letter value reductions" we need to perform on a given string in order for it to become a palindrome.

Here are the rules for this algorithm:

* Changing the value of 'd' to 'c' or 'b' to 'a' counts as a reduction of 1.
* The letter 'a' cannot be reduced any further.
* We cannot increase the value of a letter. For example, we cannot change 'c' to 'd' or 'y' to 'z'.

19:20 -- We have a function *theLoveLetterMystery* that has a single parameter *s*, which is a string that represents the word that we need to make into a palindrome.

Here's our basic setup:
```
function theLoveLetterMystery(s) {

}
```

19:38 -- Here's some pseducode I just finished writing to get me thinking about this problem:
```
// First, assess whether we are dealing with a string that has an even or odd number of charactrs. We can do this using the modulus operator.

// If the string has an odd number of characters, we'll use median as our starting point.

// If the string has an even number of characters, we'll have two starting points. Those starting points would be Math.floor(s.length / 2) and Math.ceil(s.length / 2).

// We can loop through our array seeing if startingPoint1 is equal to startingPoint2 (if there are two starting points).

// Then we'll see if startingPoint1 - 1 is equal to startPoint2 + 1. Then whether startingPoint1 -2 is equal to startingPoint2 + 2, and so on.

// Anytime startingPoint1 - n and startingPoint2 + n are not equal to each other, we'll see which one of those two has an ASCII character code that is greater.

// Whichever has an ASCII character code that is greater will be the character that we know we need to perform "value reductions" on.

// We'll perform our reductions by decrementing the ASCII character codes until both of our points are equal to each other (which could be measured by seeing whether they had either equivalent character codes, or just seeing if one of our one character strings was equal to the other)

// Each time we perform a reduction, we'll increment reductionCount by 1.

// We'll eventually break out of our loop and return reductionCount as our solution to this algorithm!
```
19:39 -- My family is pushing me to come eat as it's our last night together. I'm going to eat dinner, and then hopefully finish solving this algorithm later tonight.

UPDATE: Didn't get around to any additional coding. Will be flying back home to Vietnam tomorrow, so it will be difficult to get any coding in tomorrow also.


___
**Total time spent coding today**: 41 minutes

**Total time spent coding thus far in July 2019**: 20 hours 26 minutes

**Total lifetime hours of coding**: 670 hours 46 minutes