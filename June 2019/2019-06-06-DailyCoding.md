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
16:02 -- I'm back. I took a break for a few hours to get some walking in, take a nap, and eat lunch.

16:04 -- I now have 31 points on hackerrank with an overall ranking of 1025814.

16:09 -- I'm now working on the Diagonal Difference algorithm on hackerrank.

16:11 -- This problem is strange. It gives me a square of numbers, and I'm supposed to sum up all of the numbers going one way diagonally, and then sum up all of the numbers going the other way diagonally. Then, find the absolute difference of the two sums using
> secondary diagonal sum - primary diagonal sum = absolute difference

16:16 -- The first thing I'm trying to figure out is whether the square is always going to be 3 x 3 or if it could be of varying dimensions (4 x 4), (5 x 5), etc.

16:20 -- I was trying to figure out what the pattern would be between our values in our diagonal line. I knew that we needed to find some kind of scaleable formula if we were going to be able to solve this problem. With the primary diagonal the pattern seems to be...
1. the first value in the array
1. take the dimension of the array, for example 3 x 3, and take the first digit and add +1. In this example 3 + 1 = 4. Then we would add 4 to our current accumulator (starting at 1) and we would then select 5, and then go through the process again to select 9.
1. The same would apply for 4x4. We would select 1 then (4+1) + 1 = 6... then 6 + (4+1) = 11 then 11 + (4 + 1) = 16
1. During this process of course, we would also be adding each of the numbers together. For example, 1 + 6 + 11 + 16 = 34

16:29 -- Of course, it's also important for us to find a scaleable formula for finding the secondary diagonal. This formula is also simple.
1. The first value we select is the number that is equivalent to the dimensions of our array. For example, if our array is 5 x 5, we would first select 5.
1. Going forward we take the dimension (5 in this case), and subtract one from the dimension. 5 - 1 = 4. Then we take this number and advance this many values in the array (we'd advance to number 9 in this example).
1. Repeat the process and we get 5 + 9 + 13 + 17 + 21 = 65

16:35 -- Once we've gotten the sum of both diagonals we take the primary diagonal sum and subtract it from the secondary diagonal sum to give us our absolute difference. In other words:
>secondary sum - diagonal sum = absolute difference

We'd then take whatever we got as the absolute difference and return it to get our answer and finish the challenge. So I hope lol.

16:37 -- I have some tightness in my forearms so I'm going to take a quick break to stretch and then I'll resume coding again in another 10 minutes or so.
___
16:55 -- I'm back. Let's actually code the solution now.

16:58 -- I think this challenge is poorly explained. I still don't know if I'm going to be told the dimensions of the array, or if I just have to infer the dimensions based on the length of the array. \**sigh*\*

17:03 -- Here's what my for loop implementation looks like for my primary diagonal:
```
for (let i = 0; i < arr.length; i+= Math.sqrt(arr.length) + 1) {
 primarySum += arr[i]
}
```

17:18 -- Things are looking good so far at least according to my console ;). Now I just have to do algebraic operations between the primary sum and secondary sum:
```
function diagonalDifference(arr) {
let primarySum = 0;
let secondarySum = 0;
let squareRoot = Math.sqrt(arr.length);

for (let i = 0; i < arr.length; i+= squareRoot + 1) {
 primarySum += arr[i]
}
for (let ii = squareRoot -1; ii <= arr.length - (squareRoot - 1);ii += squareRoot - 1) {
  secondarySum += arr[ii]
}
console.log(`primary sum is ${primarySum} and secondary sum is ${secondarySum}`)
}
diagonalDifference([1, 2, 7, 4, 5, 6, 7, 8, 9])
```

17:23 -- Here's my final solution, or so I think:
```
function diagonalDifference(arr) {
let primarySum = 0;
let secondarySum = 0;
let squareRoot = Math.sqrt(arr.length);
let absoluteValueDifference;

for (let i = 0; i < arr.length; i+= squareRoot + 1) {
 primarySum += arr[i]
}
for (let ii = squareRoot -1; ii <= arr.length - (squareRoot - 1);ii += squareRoot - 1) {
  secondarySum += arr[ii]
}

absoluteValueDifference = primarySum - secondarySum;
if (absoluteValueDifference < 0) {
  return absoluteValueDifference * -1
}
return absoluteValueDifference;
}

diagonalDifference([1, 2, 7, 4, 5, 6, 7, 8, 9])
```

17:25 -- Unfortunately, it seems I've misinterpreted the problem and made things more difficult for myself... again.

I do wish that the people that wrote these challenges were better communicators. In any case, it seems that I'm receiving 2 pieces in this array. The first is a lone number that tells about the dimensions of the array, and the 2nd is an array nested inside of our array that contains all of the numbers we need.

17:37 -- I'm starting to feel annoyed with hackerrank now. Not only are the authors of the problem sets questionable communicators, but also the tests themselves seem to be faulty:

```
function diagonalDifference(arr) {
let primarySum = 0;
let secondarySum = 0;
let squareRoot = arr[0];
let absoluteValueDifference;

for (let i = 0; i < arr[1].length; i+= squareRoot + 1) {
 primarySum += arr[1][i]
}
for (let ii = squareRoot -1; ii <= arr[1].length - (squareRoot - 1);ii += squareRoot - 1) {
  secondarySum += arr[1][ii]
}
console.log(`primary sum is ${primarySum} and secondary sum is ${secondarySum}`)

absoluteValueDifference = primarySum - secondarySum;
if (absoluteValueDifference < 0) {
  return absoluteValueDifference * -1
}
return absoluteValueDifference;
}

diagonalDifference([3,[11, 2, 4, 4, 5,6, 10, 8, -12]])
```
On repl.it my answer is functional, but it's continually rejected by hackerrank.

17:43 -- Perhaps the function is not being called as such:
> diagonalDifference([3,[11, 2, 4, 4, 5,6, 10, 8, -12]])

nor as such 
>diagonalDifference([1, 2, 7, 4, 5, 6, 7, 8, 9])

But the dimensions are actually included in a one dimensional array and the first value in the array is actually the base of our grid. For example a 3 x 3 grid could potentially be:
> diagonalDifference([3, 1, 2, 3, 4, 5, 6, 7, 8, 9])

17:54 -- I've now crafted a third answer that works based on the above input:
```
function diagonalDifference(arr) {
let primarySum = 0;
let secondarySum = 0;
let squareRoot = arr[0];
let absoluteValueDifference;

for (let i = 1; i < arr.length; i+= squareRoot + 1) {
 primarySum += arr[i]
 console.log(arr[i])
}
for (let ii = squareRoot; ii <= arr.length - (squareRoot);ii += squareRoot - 1) {
  secondarySum += arr[ii]
}
console.log(`primary sum is ${primarySum} and secondary sum is ${secondarySum}`)

absoluteValueDifference = primarySum - secondarySum;
if (absoluteValueDifference < 0) {
  return absoluteValueDifference * -1
}
return absoluteValueDifference;
}

diagonalDifference([3, 11, 2, 4,
4, 5, 6,
10, 8, -12])
```
Unfortunately, it seems either I am completely misinterpreting something about the problem (seems unlikely as I produced the expected answers in repl.it using three distinct functions based on different possible inputs), OR... there is something lacking in hackerrank's tests.

18:02 -- I looked at the discussion based around this algorithm and got the idea that perhaps the problem was that I manually found the absolute value of our difference rather than using the Math.abs() method.

18:08 -- Absolutely ridiculous. Even directly copying answers others have posted won't solve this problem.

18:10 -- I cannot even get the "editorial answers" to work. This algorithm has seriously soured my experience with hackerrank. I hope this is a one-off issue with their algorithms.

If their instructions continue to be poorly communicated and I continue to have problems with their tests I'll have to switch over to codesignal or Dylan Israel's 100 algorith challenge course.

18:14 -- In any case, I feel I need a break now hahaha. I've got some client work to catch up on tonight as well as the daily developer show so I'm not sure if I'll get another coding session in tonight...
___
23:08 -- I've spent the last hour or so working on my resume. I'm not going to be able to get another "hardcore" coding session in tonight, but I will of course record another episode of the [daily developer show](https://www.youtube.com/channel/UCRUPCpCWCL6Mr-0QWNje29Q).
___
**Total time spent coding today**: 3 hours 41 minutes

**Total time spent coding  thus far in June 2019**: 14 hours 57 minutes

**Total lifetime hours of coding**: 586 hours 16 minutes

