# Thursday June 6th, 2019 Daily Coding Journal
11:10 -- Last night I stayed up almost 3 hours doing my tutorial for the first algorithm on Hackerrank. The coolest part of all... It was lots of fun!

11:12 -- I don't know if this is just a trend, or my personality, but while I can both do development, and teach development, I feel as if teaching is *suuuper energizing* while the act of doing development itself is pretty neutral.

In any case, let's get to the next algorithm on hackerrank.

11:16 -- I currently have 21 points and my rank on hackerrank is 1158959. Let's see if I can get to under 1,000,000 today!

11:30 -- So, I've been working on the *A Very Big Sum* method for several minutes now without much luck. I tried to use a for loop. Then I tried to use the reduce method. Both failed.

At first I was a bit confused because both seemed to simply concatenate the numbers in the array instead of adding them.

Well, it seems I haven't fully woken up yet. The numbers in the array weren't separated by commas. In other words, it was impossible to add the numbers in the array together because the array of my length was only 1 and thus there was only one value which I could access in my array!

Now it seems what I need to do is join the array by character to make each individual digit its own element, use the split method to get a single array again, and then iterate through the array adding each number (and perhaps use the parseInt method if my numbers somehow became strings somewhere in the process).

11:43 -- Now, using the following code block I've managed to convert my old array of [12345] into a new array [1, 2, 3, 4, 5] that is more condusive to adding values instead of merely concatenating them.
```
function aVeryBigSum(ar) {
ar = ar.join("").split("");
return ar
}
aVeryBigSum([12345])
```

11:45 -- The next step is taking our new array and adding all of the individual values together. We can do that using a for loop like so...

11:52 -- It turns out I was a little wrong. We are not yet ready to immediately add all of the numbers together yet. The reason is we don't yet have an array of numbers... We have an array of strings disguised as numbers!

11:54 -- In reality, we need to convert each string in our array into a number. We can do that using the *parseInt* method. After we convert each string into a number, we can then add all of the numbers together.

In the end, our solution to the problem should look something like this:
```
function aVeryBigSum(ar) {
ar = ar.join("").split("");
let sum = 0;
for (let i = 0; i < ar.length; i++) {
ar[i] = parseInt(ar[i]);
sum += ar[i]
}
return sum
}

aVeryBigSum([12345])
```

11:58 -- I guess not. My solution adds all of the numbers in an array, but it didn't pass. Perhaps I misindentified what we're supposed to be doing in this algorithm...

11:59 -- Perhaps the problem is that I made the assumption that in every case the length of our array was only going to be 1...

12:03 -- Yep, I unnecessarily complicated things. This problem is actually super simple. We're just given an array of numbers and we need to add all of them together. 

Each number is a separate value in the array. We don't have to worry about dealing with an array that only has one value, and forcing that array to have multiple values.

In other words, the solution is suuuuper simple:
```
function aVeryBigSum(ar) {
  let sum = 0
for (let i = 0; i < ar.length; i++) {
  sum += ar[i]
}
return sum
}
```
If you're still lost, don't worry. Let's break it down.

\#1 --  We're given an empty function.
```
function aVeryBigSum(ar) { }
```
\#2 -- We create a sum varable and initialize it to 0.
```
function aVeryBigSum(ar) {
    let sum = 0;
}
```
\#3 -- We write a for loop. We initialize 'i' to 0, tell the for loop to continue running as long as 'i' is less than the length or our array, and each time we iterate (go through the loop) we add one to 'i'.
```
function aVeryBigSum(ar) {
    let sum = 0;
    for (let i = 0; i < ar.length; i++) {

    }
}
```
\#4 -- Now, we need to actually do something within our for loop. We want to add each value in our arr to our sum variable. We can do that using +=. We can access each individual array item using *ar[i]*.
```
function aVeryBigSum(ar) {
    let sum = 0;
    for (let i = 0; i < ar.length; i++) {
 sum+= ar[i] 
    }
}
```
\#5 -- Finally, we need to make sure we actually save all of the information that we're putting into our sum variable. Currently we're adding all of our array items to our sum, but we're not actually doing anything with that data.

We can actually save and do something with the information we've collected by returning our sum after our for loop has finished running, but before we exit our aVeryBigSum function.
```
function aVeryBigSum(ar) {
    let sum = 0
    for (let i = 0; i < ar.length; i++) {
        sum += ar[i]
    }
    return sum
}
```
I hope you found all of this useful! :D
___
**Total time spent coding today**: 

**Total time spent coding  thus far in June 2019**: 

**Total lifetime hours of coding**: 

