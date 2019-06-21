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
**Total time spent coding today**: 

**Total time spent coding thus far in June 2019**: 

**Total lifetime hours of coding**: 