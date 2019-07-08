# Sunday July 7th, 2019 Daily Coding Journal

13:47 -- Here we go. Let's do some coding.

14:14 -- Feeling a bit unmotivated today. Tried doing some navbar design, but couldn't really get my brain to engage after getting the basics down. For that reason, I'm just going back to JavaScript.

14:17 -- Be back later.
___
22:49 -- My first coding session today was a bit of a nightmare -- I had neither focus nor motivation.

Let's try to do better tonight.

22:53 -- I started working on the [Caesar Cipher problem on HackerRank](https://www.hackerrank.com/challenges/caesar-cipher-1/problem).

22:54 -- A few minutes in, here's where I'm at:
```
function caesarCipher(s, k) {

for (let i = 0; i < s.length; i++) {
  console.log(s[i])
 }
}
```
22:55 -- Now, I need to add plus 3 to the ASCII value of each character in my string, and if the string ends up being outside the range of a-z, or A-Z, I'll have to go back to the beginning of the alphabet somehow.

23:11 -- I'm not really in the mood to program, but I'm bruteforcing things. Here's where I'm at now:
```
function caesarCipher(s, k) {

for (let i = 0; i < s.length; i++) {
  if (s[i].toLowerCase() === s[i]) {
    if ((s[i].charCodeAt() + k) <= 122) {
      console.log(s[i].charCodeAt() + k + " successful shift")
    }
    else {
      console.log(String.fromCharCode(Math.abs(122 - (120 + 3)) +  96))
    }
  }
 }
}
```
23:30 -- I've created a solution that passes about half of HackerRank's test cases:
```
function caesarCipher(s, k) {
let result = [];
for (let i = 0; i < s.length; i++) {
  if (s[i].toUpperCase() === s[i] && s[i].toLowerCase() === s[i]) {
    result.push(s[i])
  }
  else if (s[i].toLowerCase() === s[i]) {
    if ((s[i].charCodeAt() + k) <= 122) {
      result.push(String.fromCharCode(s[i].charCodeAt() + k))
    }
    else {
      result.push(String.fromCharCode(Math.abs(122 - (s[i].charCodeAt() + k)) +  96))
    }
        }
    else if (s[i].toUpperCase() === s[i]) {
        if (s[i].charCodeAt() + k <= 90) {
          result.push(String.fromCharCode(s[i].charCodeAt() + k))
    }
    else {
      result.push(String.fromCharCode(Math.abs(90 - (s[i].charCodeAt() + k)) +  64))
    }
        }
  }
return result.join("")
}
```
23:31 -- The only problem is that the above solution cannot pass HackerRank's test cases that use large numbers. I'll figure out exactly why later.

23:36 -- I took a quick bathroom break, but afterwards a possible solution came to my attention.

Because we know exactly how many characters we need to loop through, or to speak more precisely... how many available ASCII characters or alphabet characters we're working with, we know that if we shift a letter 26 positions, we'll end up in the exact same spot.

Thus, if our value for *k*, the number of position we're shifting our characters is greater than 26, we can use the modulus operator and just shift a number of spots equal to the remainder.

23:41 -- As I suspected, in cases where *k* was greater than 26, setting *k* equal to *k* modulus operator 26 produced the actual number of positions we needed to shift.

I made this change, and doing so allowed me to successfully pass all of this challenge's user tests.

Here's my final solution for this algorithm!
```
function caesarCipher(s, k) {
let result = [];
for (let i = 0; i < s.length; i++) {

  if (k > 26) {
    k = k % 26
  }

  if (s[i].toUpperCase() === s[i] && s[i].toLowerCase() === s[i]) {
    result.push(s[i])
  }
  else if (s[i].toLowerCase() === s[i]) {
    if ((s[i].charCodeAt() + k) <= 122) {
      result.push(String.fromCharCode(s[i].charCodeAt() + k))
    }
    else {
      result.push(String.fromCharCode(Math.abs(122 - (s[i].charCodeAt() + k)) +  96))
    }
        }
    else if (s[i].toUpperCase() === s[i]) {
        if (s[i].charCodeAt() + k <= 90) {
          result.push(String.fromCharCode(s[i].charCodeAt() + k))
    }
    else {
      result.push(String.fromCharCode(Math.abs(90 - (s[i].charCodeAt() + k)) +  64))
    }
        }
  }
return result.join("")
}
```
23:47 -- I'll explain my solution in more detail for you in tomorrow's journal entry. See you then!
___
**Total time spent coding today**: 1 hour 29 minutes

**Total time spent coding thus far in July 2019**: 18 hours

**Total lifetime hours of coding**: 668 hours 21 minutes