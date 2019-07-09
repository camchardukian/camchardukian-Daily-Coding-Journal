# Monday July 8th, 2019 Daily Coding Journal
8:26 -- I'm up. Here we go!

8:27 -- Yesterday I solved the Caesar Cipher algorithm on HackerRank. Today, I'll start off by explaining my solution from yesterday to you.

8:28 -- Julius Caesar supposedly used a letter shifting technique we now call a 'Caesar cipher' or 'Caesar's cipher' as a way of encryting his written communication.

This method of encryption basically takes the alphabet and shifts it a number of positions to the right or left.

We then take the origin alphabet, line it up with the new alphabet, and whenever we write a word, we take the letter we originally wrote, and substitute in the letter that aligned with it.

Read more on [Wikipedia about Caesar's cipher here](https://en.wikipedia.org/wiki/Caesar_cipher).

8:35 -- We're going to write a Caesar's cipher that shifts each letter of the alphabet. We may for example shift our alphabet three positions to the right (with the end of the alphabet looping back to the beginning).

In this case, 'abc' would become 'def', 'xyz' would become 'abc' and so on.

We have a function *caesarCipher* that has two parameters:
* *s*: a string in cleartext (with cleartext being a term used to describe text or data that is immediately processable by humans and thus probably not at all encrypted).

* *k*: An integer which represents how many places we're rotating our alphabet.

Here's our basic setup:
```
function caesarCipher(s, k) {

}
```
8:42 -- We're going to do two things to get started. First, we're going to declare a variable *result*.

We'll initialize this variable to an empty array.

We're also going to create a loop that'll iterate through each character in our string *s*.
```
function caesarCipher(s, k) {
    let result = [];
    for (let i = 0; i < s.length; i++) {
    }
}
```
8:44 -- Next, we're going to calculate how many positions we "actually" need to shift our alphabet to the right.

Because there are only 26 letters in the alphabet, we know that the maximum number we can shift our alphabet by is 25.

It wouldn't make sense to try to shift our alphabet by 30,000 spaces for example. We would have to loop through our alphabet well over 1,000 times to perform this type of shift.

For that reason, we're going to say that any time our variable *k* is greater than or equal to 26, we're going to take *k* and set it equal to the result of *k* modulus operator 26.

*Why are we using the modulus operator with 26?* The answer is pretty simple -- we're finding out how many positions we "actually" need to shift our alphabet.

If the initial value of *k* was 26, we'd know that it wouldn't actually be necessary to do any shifting at all.

If the initial value of *k* was 28, we'd know we'd have to shift our alphabet two places to the right.

Basically, we're dividing the initial value of *k* by 26, and then we know that whatever the remainder is (which is exactly what the modulus operator is used to calculate), that's how many positions to the right we "actually" need to shift our alphabet.
```
function caesarCipher(s, k) {
    let result = [];
    for (let i = 0; i < s.length; i++) {

        if (k > 25) {
            k = k % 26
        }
    }
}
```
8:58 -- Now that we've gotten our alphabet down, we're going to look at the individual characters in our string.

We know that anytime we're dealing with non-alphabet characters (spaces, numbers, dashes, etc), we won't be performing any shifts on these characters and just want to return them as is.

We know that if a character is equal to the uppercase version of itself, that that character is already an uppercase letter.

We know that if a character is equal to the lowercase version of itself, that that character is already a lowercase letter.

But, if a character is equal to the upper AND lower case version of itself that means we're not dealing with a letter.

It's impossible for 'a' to be equal to 'a' and 'A' at the same time. However, a "capital" or uppercase dash is exactly the same as a lowercase one (because uppercase and lowercase don't exist with non-alphabet characters).

Thus, we know that if a character can simultaneously be equal to both the uppercase and lowercase verion of itself, that character is not part of the alphabet and we can just return it as is (or in this case, push it to our results array for later returning).
```
function caesarCipher(s, k) {
let result = [];
for (let i = 0; i < s.length; i++) {

  if (k >= 26) {
    k = k % 26
  }

  if (s[i].toUpperCase() === s[i] && s[i].toLowerCase() === s[i]) {
    result.push(s[i])
  }
 }
}
```
9:06 -- On the other hand, if a character is equal to the lowercase version of itself (s[i].toLowerCase() === s[i]), that character is obviously a lowercase letter. 

Because we know that the lowercase letters of the alphabet correspond with ASCII values 97-122, we can say that if a given letter's ASCII value plus *k* is equal to or less than 122, we can push that character's value (along with the shift of *k*) to our results array.

For example if we have letter 'a' which has an ASCII value of 97, and a *k* value of 3, we can add both of them together.

This will give us 100, which we can convert to 'd' using String.fromCharCode().

Of course, we also know that if our character's ASCII value plus *k* was greater than 122, we'd know that we'd need to loop through our alphabet back to the beginning.

We can do this using 
> result.push(String.fromCharCode(Math.abs(122 - (s[i].charCodeAt() + k)) +  96))

What we're doing with the above code is basically getting a character from a certain ASCII code.

We're calculating the ASCII code/value by taking the absolute value of 122 (the maximum ASCII code for lowercase letters) and subtracting from it (122) by *k* and the result of whatever ASCII value our current character is equal to (s[i].charCodeAt()). Finally, we're adding 96.

Now, let's understand conceptually *why* we're doing all of the above. Because we know that the last letter in the alphabet 'z' has an ASCII code of 122, anything above 122 is "beyond" our alphabet.

Thus, by subtracting our large number (s[i].charCodeAt() + k) from 122, we can see how many values we need to shift our alphabet.

Let's take (s[i].charCodeAt() + k) which evaluates to be 130. 122 - 130 = -8. We obviously don't want to go *negative* 8 places beyond the value of 'z' (because that wouldn't loop back through to the beginning of the alphabet as we want).

We want to go a positive number of places beyond the value of 'z'. Thus, we'll take the absoluate value of 122 - 130 which in this case, would equal positive 8.

We can then take this positive value of 8,and add it to 96 to calculate what our final value of ASCII is that we'll generate a string from and push to *result*!

Where did 96 come from? Think of it like this. The smallest possible ASCII code for an English lowercase letter is 97. 

If we go one position past 'z', when we loop around to the beginning of our alphabet we want to produce an 'a'.

96 plus 1 (the number of places we're going past 'z') is equal to the ASCII character code for lowercase 'a'.
```
function caesarCipher(s, k) {
let result = [];
for (let i = 0; i < s.length; i++) {

  if (k >= 26) {
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
  }
}
```
9:39 -- If you followed along with the last step, we're going to go through almost the same process again.

Only this time, we'll change some of the ASCII codes because we're dealing with uppercase letters (ASCII codes 65-90) rather than lowercase letters (ASCII codes 97-122).
```
function caesarCipher(s, k) {
let result = [];
for (let i = 0; i < s.length; i++) {

  if (k >= 26) {
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
}
```
9:42 -- Once we break out of all of our loops (which signified we've done all of the necessary shifts on our letters and pushed all letter and non-letter to *result*), we can then return *result.join("")* as our solution to this algorithm!

Note: The reason we're returning *result.join("")* rather than merely returning *result* is because we want to return a string as our solution to this algorithm rather than an array.
```
function caesarCipher(s, k) {
let result = [];
for (let i = 0; i < s.length; i++) {

  if (k >= 26) {
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
9:45 -- This was a long algorithm explanation. Congratulations, you've made it all the way to the end! :D

9:54 -- Explaining that last algorithm took waaaaaay longer than I expected. It's all good though.

Explaining everything in more detail really made me think about my solution. I feel solving this last algorithm really helped strengthen my comfort with ASCII codes, as well as the charCodeAt() and String.fromCharCode() methods.

9:55 -- I now have 882.92 points which is good enough for a rank of 85,718 on HackerRank's global algorithms & data structures leaderboard.

9:57 -- During my next coding session, I'll attempt to solve [The Love Letter Mystery](https://www.hackerrank.com/challenges/the-love-letter-mystery/problem) algorithm.
___
23:40 -- Ended up spending a lot of time with family today because of the fact that I'll be headed back to Vietnam soon.

I also lost a couple hours finding a place to stay on airbnb for my first few weeks back.

Tomorrow I'll try to get at least an hour of coding in. It's unlikely I'll get a ton of coding in this week because of needing to say goodbyes, having a long flight back to Asia, and being jetlagged/finding work when I get back.

In any case, I'm excited to see how the next few weeks play out.
___
**Total time spent coding today**: 1 hour 39 minutes 

**Total time spent coding thus far in July 2019**: 19 hours 44 minutes

**Total lifetime hours of coding**: 670 hours 4 minutes