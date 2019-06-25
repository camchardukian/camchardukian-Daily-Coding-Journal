# Monday June 24th, 2019 Daily Coding Journal

12:29 -- I finally finished my developer resume yesterday. I'll have some family members look over it to help me identify areas that are too wordy, or difficult to understand.

Then... I think I'll be in business ;)

12:30 -- In any case, I'm going to quick move my clothes over from the washer to the dryer. Then, I'll try to solve the HackerRank in a String algorithm before making a trip to the dentist.

12:40 -- I'm back, I've only got about 30 minutes before I need to head out, but let's see if we can get anything done.

12:42 -- Because I'm a bit short on time, I'm not going to go in-depth about explaining this problem now. I'm just going to try to solve it, document my progress, and explain things later.

12:46 -- Basic function setup:
```
function hackerrankInString(s) {
console.log(s)

}
```
12:55 -- Final solution:
```
function hackerrankInString(s) {
let hackerrankArray = ['h', 'a', 'c', 'k', 'e', 'r', 'r', 'a', 'n', 'k'];
for (let i = 0; i < s.length + 1; i++) {
  if (hackerrankArray.length > 0) {
  if (s[i] === hackerrankArray[0]) {
    hackerrankArray.shift()
  }
  }
  else {
    return "YES"
  }
}
return "NO"
}
```
WOW! We ended up solving this algorithm **super** quickly. I need to arrange my commit this journal entry to GitHub, hang my clothes, eat an apple, brush my teeth, and change into nicer clothes before going out.

12:56 -- I'll explain my algorithm solution during my next coding session -- perhaps even in the car on the way to the dentist if my mom doesn't find my anti-socialness too rude hahaha.
___
17:01 -- On the way home from the dentist now...

17:02 -- We have a function *hackerrankInString* that has a single parameter *s*. Our goal is to identify whether if we can spell the word 'hackerrank' by taking sequential (though not necessarily consecutive) characters from our string *s*.

Here's our basic function setup:
```
function hackerrankInString(s) {
 
}
```
17:04 -- Next, we're going to create a variable *hackerrankArray* and initialize it to an array where each sequential item matches the corresponding letter from the word 'hackerrank'.

In other words, the first item in our array will be 'h', the second item will be 'a', the third item will be 'c', and so on.
```
function hackerrankInString(s) {
let hackerrankArray = ['h', 'a', 'c', 'k', 'e', 'r', 'r', 'a', 'n', 'k'];
}
```
17:06 -- Now that we have our array *hackerrankArray*, we can use a for loop to iterate through it. Each time through our array, we'll evaluate whether the length of *hackerrankArray* is greater than 0.

If so, we'll check to see whether our current value in the string *s*, is equivalent to the first remaining letter in *hackerrankArray*.

If so, we'll use the shift method on *hackerrankArray* which basically serves to kick the first item in *hackerrankArray* out of the array.
```
function hackerrankInString(s) {
let hackerrankArray = ['h', 'a', 'c', 'k', 'e', 'r', 'r', 'a', 'n', 'k'];
for (let i = 0; i < s.length + 1; i++) {
  if (hackerrankArray.length > 0) {
  if (s[i] === hackerrankArray[0]) {
    hackerrankArray.shift()
    }
  }
 }
}
```
17:11 -- We'd then go through the next iteration of our loop. If at anytime, however, *hackerrankArray* had a length of 0, we'd return "YES" as our solution to this algorithm.

*Why?* The answer is simple. Any scenario in which *hackerrankArray* had a length of 0 would be a scenario in which we'd already shifted (and thus encountered in sequential order) every letter necessary to spell 'hackerrank'.

Also notice that we are iterating through our array as long as our variable *i* is less than **s.length + 1**.

The reason for this is that in some scenarios, the very last letter of *s* may be the letter 'k' we need to spell 'hackerrank'.

Thus, after we finish iterating through all of the letters in *s*, we still need to go through our loop one more time just in case the last letter of *s* was significant in changing the length of *hackerrankArray* from 1 to 0.

While this scenario would probably be fairly rare, it is important to account for it.

Of course, if despite all of our previous steps we break out of our loop without ever returning "YES", we'd then return "NO" as our solution to this algorithm.
```
function hackerrankInString(s) {
let hackerrankArray = ['h', 'a', 'c', 'k', 'e', 'r', 'r', 'a', 'n', 'k'];
for (let i = 0; i < s.length + 1; i++) {
  if (hackerrankArray.length > 0) {
  if (s[i] === hackerrankArray[0]) {
    hackerrankArray.shift()
  }
  }
  else {
    return "YES"
  }
}
return "NO"
}
```
17:19 -- Way to stick with things! Hopefully by this point you've gotten at least a surface level understanding of this algorithm down.

Keep practicing, and you'll slowly internalize different concepts. Given enough time, eventually things will start to click! :D

17:25 -- I now have 571 points which is good enough for a rank of 142,407 on HackerRank's global leaderboard.

17:27 -- During my next coding session I'll solve the "[Lisa's Workbook](https://www.hackerrank.com/challenges/lisa-workbook/problem)" algorithm.
___
UPDATE: After my last coding session, I ended up having dinner, spending a couple hours showing my parents some pictures of my travels and life abroad, and then unfortunately I wasted a few hours.


___
**Total time spent coding today**: 58 minutes

**Total time spent coding thus far in June 2019**: 58 hours 33 minutes

**Total lifetime hours of coding**: 630 hours 16 minutes