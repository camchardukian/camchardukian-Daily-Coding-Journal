# Monday June 17th, 2019 Daily Coding Journal

9:40 -- Spent the last 5 minutes or so commiting my coding journal entry from yesterday.

Let's get back to the [divisible sum pairs algorithm](https://www.hackerrank.com/challenges/divisible-sum-pairs/problem).

9:42 -- I'm sensing the need for a nested for loop...

9:51 -- Making progress...
```
function divisibleSumPairs(n, k, ar) {
console.log(`n = ${n} and is the integer length of the array "ar"`)

console.log(`k = ${k} and is the integer we are performing division with`)

console.log(`ar = ${ar} and is our array of integers`)

for (let i = 0; i < ar.length - 1; i++) {
  for (let ii = i + 1; ii < ar.length; ii++) {
    console.log(`i:${ar[i]} and ii:${ar[ii]} have a sum of ${ar[i] + ar[ii]} `)
  }
}
}
```
10:04 -- Solved the algorithm. Here's my final solution:
```
function divisibleSumPairs(n, k, ar) {
  let results = [];

for (let i = 0; i < n - 1; i++) {
  for (let ii = i + 1; ii < n; ii++) {
    if ((ar[i]+ar[ii]) % k === 0) {
      results.push(`${i},${ii}`)
    } 
  }
}
return results.length
}
```
10:06 -- While the code I wrote to get to this point may have been a bit messy, the solution itself is pretty simple. Here's what we're doing.

10:07 -- First, we have a function *divisbleSumPairs* that has parameters of *n*, *k*, and *ar*.

*n* takes in an argument that represents the integer length of the array, the value passed to *k* is what we will use as a divisor, and the value passed to *ar* will be our array of integers.

I've also initialized a results variable to an empty array, which we will later use when we need to return our output for the algorithm.
```
function divisibleSumPairs(n, k, ar) {
  let results = [];
}
```
10:13 -- The next thing we need to do is loop through and add the items in our array. If our array was [1, 3, 5, 10] for example, we'd need to first see what do 1 + 3 equal, then 1 + 5, then 1+ 10. Then... we'd go to the next number and see 3 + 5, 3 + 10, etc.

We can do this by using a nested array.
```
function divisibleSumPairs(n, k, ar) {
  let results = [];

for (let i = 0; i < n - 1; i++) {
  for (let ii = i + 1; ii < n; ii++) {
    if ((ar[i]+ar[ii]) % k === 0) {
      results.push(`${i},${ii}`)
    } 
  }
  return results.length
}
```
Notice that in the code above, besides simply adding every possible combination of integer pairs from the array, we also used the modulus operator (%).

The reason we used the modulus operator is because through using it we can see if numbers are evenly divisble by something.

In this case, we used the modulus operator to evaluate whether a pair of integers (ar[i] + ar[ii]) divided by *k* would have a remainder of **0**.

If so, we pushed that pair of integers to our result array.

Finally, we returned the length of our results array as our output and final solution to this algorithm.

While we could've used a simple counter variable and just incremented it each time we found an integer pair evenly divisible by *k*, I thought saving the integer pairs may be useful for some other unspecified future operation (if this were a real-world example).

Of course, you could also argue that having to return the length of the *results* array rather than simply displaying the number assigned to a counter variable results in some extra processing time.

That may be true. Alas, the ideal solution depends on the intended real-world use case, and is beyond the scope of this algorithm.

Regardless, I hope you found my explanation of this algorithm useful!

10:28 -- I now have 126 points on HackerRank which is good for a global ranking of 531,606.

10:30 -- After I commit everything to GitHub and take a break, I'll then start working on the [Bon Appétit algorithm on HackerRank](https://www.hackerrank.com/challenges/bon-appetit/problem).
___
11:19 -- Commited everything to GitHub, did 20 minutes of exercise, got some water... now let's work on the [Bon Appétit algorithm on HackerRank](https://www.hackerrank.com/challenges/bon-appetit/problem).

11:21 -- Let's define the problem. It looks like we've got two people sharing a meal at a restaurant (Anna and Brian).

They agree to share the bill for the meal equally, with the exception that Brian alone will pay for anything he orders that Anna is allergic to.

It looks like what we need to do is subtract the item Anna is allergic to from the bill, then divide the bill by two.

If there is a discrepancy between this number, and the number Anna actualy paid, we need to log to the console how much money Brian should refund to Anna.

Otherwise, we simply print 'Bon Appetit' to the console.

I'm going to solve this problem, documenting my progress along the way. Then, I'll explain the solution later.

11:28 -- Basic function:
```
function bonAppetit(bill, k, b) {

}
```

11:30 -- Working in Repl.it:
```
function bonAppetit(bill, k, b) {

}

bonAppetit([2, 1, 8, 10], 1, 10)
```
11:32 -- Totaling up how much everything together costs...
```
function bonAppetit(bill, k, b) {
  let total = 0;
for (let i = 0; i < bill.length; i++) {
total+= bill[i]
}
}
```
11:38 -- Added a little bit of humor:
```
function bonAppetit(bill, k, b) {
  let total = 0;
for (let i = 0; i < bill.length; i++) {
total+= bill[i]
}
if ((total - bill[k])/ 2 === b) {
  console.log('Bon Appetit')
}
else if ((total - bill[k])/ 2 < b) {
console.log("refund")
}
else if ((total - bill[k])/ 2 > b)  {
  console.log("Anna is trying to run away with the $$$")
}
else {
  console.log("Please double check the inputs and try again.")
  }
}
```
11:42 -- Wow, we solved this problem surprising quickly! Here's my final solution:
```
function bonAppetit(bill, k, b) {
  let total = 0;
for (let i = 0; i < bill.length; i++) {
total+= bill[i]
}
if ((total - bill[k])/ 2 === b) {
  console.log('Bon Appetit')
}
else if ((total - bill[k])/ 2 < b) {
console.log(b - (total - bill[k])/ 2)
}
else if ((total - bill[k])/ 2 > b)  {
  console.log("Anna is trying to run away with the $$$")
}
else {
  console.log("Please double check the inputs and try again.")
  }
}
```
11:46 -- Let's break it down. The first thing we need to do is write a function *bonAppetit* that has three parameters: *bill*, *k*, and *b*.

The value passed to *bill* will be an array of integers representing the cost of each item ordered.

*k* is an integer that represents which item in the *bill* array Anna doesn't eat.

*b* is how much money Anna originally contributed to the bill.

Here's our basic function, and function call:
```
function bonAppetit(bill, k, b) {

}
bonAppetit([2, 1, 8, 10], 1, 10.5)
```
Also, a quick note: I'm showing this function call to help you visualize what we're working with. You shouldn't actually include it when submitting your algorithm (doing so will result in your solution failing the test cases).

11:53 -- Next, we need to total the cost of all of the items ordered to figure out how much their dinner actually costs.

We can do this by intializing a variable *total* to 0, and then using a for loop and adding (incrementing by the value of) each item in our bill array:
```
function bonAppetit(bill, k, b) {
  let total = 0;
for (let i = 0; i < bill.length; i++) {
total+= bill[i]
}
}
```
The final thing we need to add is our conditional logic. If we take our *total* which represents how much the meal costs, and minus the value of the item Anna was allergic to *bill[k]*, we can divide it by two to see how much money Anna should pay.

If the result of the previous operation is equal to what Anna actually paid *b*, we log 'Bon Appetit' to the console. 

If Anna paid too much, we can calculate her change by subtracting how much she should have paid by what she actually paid.

For humor purposes, I also added a scenario in which Anna runs away with extra money, and an all encompassing error message (if for example the user passed a string instead of an integer to our *b* variable).

Final solution:
```
function bonAppetit(bill, k, b) {
  let total = 0;
for (let i = 0; i < bill.length; i++) {
total+= bill[i]
}
if ((total - bill[k])/ 2 === b) {
  console.log('Bon Appetit')
}
else if ((total - bill[k])/ 2 < b) {
console.log(b - (total - bill[k])/ 2)
}
else if ((total - bill[k])/ 2 > b)  {
  console.log("Anna is running away with the extra $$$")
}
else {
  console.log("Please double check the inputs and try again.")
  }
}
```
12:14 -- Just finished commiting that solution to GitHub. I'm going to commit this journal entry to GitHub, and then maybe take a nap.

I made a conscious decision today that I will not eat until I've spent 4 hours coding and I will not browse the internet unless I spend at least 6 hours coding today. As of now, I'm at about 2 solid hours of coding today.

In any case, I need to take a break. I'm hungry so I need to relax, refresh my mind, and get back to coding so I can eat something! :D
___
15:38 -- I committed everything to GitHub and got a few hours of sleep. Now it's time to continue working so I can eventually get dinner today haha.

15:40 -- I currently have 136 points on HackerRank which is good for a global rank of 504,390.

15:42 -- I'm now working on the [Sock Merchant algorithm on HackerRank](https://www.hackerrank.com/challenges/sock-merchant/problem).

15:43 -- This problem seems fairly simple. We have a function *sockMerchant* that has two parameters. Those parameters are *n* which represents the number of socks in the pile, and *ar* which is an array of integers that represent unique color values (think of these numbers representing colors kind of like hexcode, only there is no need for a true visual representation as they are more or less theoretical colors.).

15:56 -- The problem seemed simple in theory, now I'm trying to figure out if I should try to use a nested for loop, or whether dividing by two and using the Math.floor() method would be more efficient.

15:58 -- Some random experimental code thus far:
```
function sockMerchant(n, ar) {
console.log(`${n} is the number of socks`)
let current = 0
for (let i = 0; i < n; i++){
  console.log(ar[i])
}
}

sockMerchant(9, [1, 2, 2, 3, 4, 1, 3, 1, 10]);
// n: the number of socks in the pile
// ar: the colors of each sock
```
16:03 -- Brainstorming... Here's my idea:
>Check if current value of ar[i] has already been evaluated. Is so, move on to the item in the array. If not, push the value of ar[i] to our alreadyEvaluated array, and then count the number of times the value of ar[i] occurs throughout ar. Then, we can divide by two and use Math.floor to figure out how many pairs there are for that integer value.

16:06 -- Baby steps of progress...
```
function sockMerchant(n, ar) {
let alreadyEvaluated = [];
for (let i = 0; i < n; i++){
  if (alreadyEvaluated.indexOf(ar[i])!= -1) {
    console.log("already")
  }
  else {
    console.log("not yet, but coming right up!")
        alreadyEvaluated.push(ar[i])
  }
}
}
sockMerchant(9, [1, 2, 2, 3, 4, 1, 3, 1, 10]);
```
16:12 -- Another five minutes of work:
```
function sockMerchant(n, ar) {
let alreadyEvaluated = [];
let numberOfPairs = 0;
for (let i = 0; i < n; i++){
  if (alreadyEvaluated.indexOf(ar[i])!= -1) {
  }
  else {
        alreadyEvaluated.push(ar[i])
        for (let ii = i + 1; ii < n; ii++) {
          console.log(ar[ii])
        }
        console.log(`break`)
  }
}
}
```
16:28 -- I've solved the algorithm. It took a bit longer than expected because for wateer reason it took me ages to identify that one of my variables was called *numbersOfSocks* instead of *numberOfSocks* and I wasted a lot of time trying to assign a value to a variable that was never declared.

In any case, here's my solution:
```
function sockMerchant(n, ar) {
let alreadyEvaluated = [];
let numberOfPairs = 0;
let numberOfSocks = 1;
for (let i = 0; i < n; i++){
  if (alreadyEvaluated.indexOf(ar[i])!= -1) {
  }
  else {
        alreadyEvaluated.push(ar[i])
         numberOfSocks = 1;
        for (let ii = i + 1; ii < n; ii++) {
          if (ar[i] === ar[ii]) {
numberOfSocks+=1
          }
        }
        numberOfPairs+=Math.floor(numberOfSocks/2)
  }
}
return numberOfPairs
}
```
I'm going to take a quick break to go to the bathroom, and stretch. Then I'll come back and explain my solution.

16:37 -- Let's gooooo!

16:38 -- The first thing we need to do is define a function *sockMerchant* that has the parameters *n* and *ar*.

*n* represents how many total socks we have in our sock pile (or in programming terms, the length of our array).

*ar* represents the color (such as a rgb value or hexcode) of each individual sock.
```
function sockMerchant(n, ar) {

}
```
16:40 -- I also think it's important that we define three variables before we go any further. The first of those three variables is *alreadyEvaluated*, which is initialized to an empty array, and will be used for checking whether we've already gathered all of the color socks of that color value.

For example, if we already gathered all of the blue socks, counted them, and performed our calculation; it isn't necessary for us to loop through everything and repeat said calculations if we encounter another blue sock.

The second variable is *numberOfSocks* which is initialized to 1 (because if we're evaluating a given color of socks from our array we know that there will be at least one of that color.). Whenever we find a color of sock that hasn't yet been evaluated, we'll loop through our array and total all of that color.

The third and final variable is *numberOfPairs*. Our *numberOfPairs* variable is initalized to 0, but may be incremented... we'll get to that later.

Now that we understand all of the variables, I'll show you the final solution and explain more in-depth about how all of the variables interact.
```
function sockMerchant(n, ar) {
let alreadyEvaluated = [];
let numberOfSocks = 1;
let numberOfPairs = 0;
for (let i = 0; i < n; i++){
  if (alreadyEvaluated.indexOf(ar[i])!= -1) {
  }
  else {
        alreadyEvaluated.push(ar[i])
         numberOfSocks = 1;
        for (let ii = i + 1; ii < n; ii++) {
          if (ar[i] === ar[ii]) {
numberOfSocks+=1
          }
        }
        numberOfPairs+=Math.floor(numberOfSocks/2)
  }
}
return numberOfPairs
}
```
16:48 -- From top to bottom, here we go.
 1. First we define our function, its parameters, and the variables we just finished discussing.

 1. Next, we write a for loop that'll loop through all of the socks in our pile.

 1. Within the for loop, we utilize the indexOf() method to evaluate whether the current sock color (value of ar[i]) has already been evaluated. If so, we do nothing and will move on to the next sock (item in the array *ar*). If not, we'll continue to the next step.

 1. If we haven't yet evaluated a given sock color, the first thing we need to do is push that sock color to our *alreadyEvaluated* array. This will prevent us from "double dipping" and wasting unnecessary resources evaluating it again later.

 1. After pushing the sock color to *alreadyEvaluated*, we then will loop through our *ar* array and compare our current sock with all of the remaining socks in the pile (one by one). Anytime the color of our current sock is the same as one of the socks in the pil, we increment numberOfSocks by one.

 1. After we go through all of the socks in the pile, we need to add the number of pairs to our *numberofPairs* variable. We do this by incrementing *numberOfPairs* by the result of Math.floor(numberOfSocks/2).

 1. If we haven't finished going through all of the possible color combination, we'll go back to our initial for loop from step #1 and repeat the process.

 1. After completing all of the previous steps, we return our *numberOfPairs* variable as our solution to the algorithm!

17:03 -- That was a lot of typing. My hands are getting too cold sitting in the basement now, and my back is getting a bit sore.

I'm going to exercise a bit, then come back after I've taken care of my body.
___
17:58 -- I got some exercise, warmed my hands up, and chatted with my parents a bit. Now, it's time to get back to work.

17:59 -- I now have 146 points on HackerRank for a global rank of 479,710.

18:00 -- I'm now working on the [Cats and a Mouse algorithm on HackerRank](https://www.hackerrank.com/challenges/cats-and-a-mouse/problem).

18:03 -- This problem isn't too difficult. We've got a mouse that's running away from two cats. The two cats travel at equal speeds. The mouse doesn't move. Our job is to determine which cat will catch the mouse first. Or, if they both reach the mouse at the same time, the cats will fight and we'll log 'Mouse C' to the console.

18:05 -- I'm going to document my progress as I solve this problem and then I'll explain my solution after I've finished everything.

18:11 -- I'm making progress...
```
function catAndMouse(x, y, z) {
console.log(`Cat A is at ${x} Cat B is at ${y} and the mouse is at ${z}`)
console.log(Math.abs(x-z))
console.log(Math.abs(y-z))
}

catAndMouse(-1, 3, 1)
```
18:16 -- My solution seems to work in repl.it, but is getting rejected on HackerRank for some reason. Let's do some investigating...
```
function catAndMouse(x, y, z) {
console.log(`Cat A is at ${x} Cat B is at ${y} and the mouse is at ${z}`)
if (Math.abs(x-z) > Math.abs(y-z)) {
  console.log("Cat B")
}
else if (Math.abs(x-z) < Math.abs(y-z)) {
  console.log("Cat A")
}
else if (Math.abs(x-z) === Math.abs(y-z)) {
  console.log('Mouse C')
}
else {
  console.log("error: unexpected input")
}
}
```
18:19 -- That was easy enough. It looks like I just had to remove my console.log() calls and replace them with equivalent return statements:
```
function catAndMouse(x, y, z) {
if (Math.abs(x-z) > Math.abs(y-z)) {
  return ("Cat B")
}
else if (Math.abs(x-z) < Math.abs(y-z)) {
  return ("Cat A")
}
else if (Math.abs(x-z) === Math.abs(y-z)) {
  return ('Mouse C')
}
else {
  return ("error: unexpected input")
}
}
```
18:20 -- I'm going to go to the bathroom, and stretch. Then I'll explain my solution and commit everything to GitHub.

18:27 -- Going to do a little exercise. Back soon...
___
18:51 -- I'm back. Body is feeling good. Let's explain the [HackerRank Cats and a Mouse algorithm](https://www.hackerrank.com/challenges/cats-and-a-mouse/problem).

18:52 -- To start with, we define a function *catAndMouse* that has three parameters *x*, *y*, and *z*. Our variables represent the starting points of our different animals. *x* represents 'Cat A', *y* represents 'Cat B', and *z* represents 'Mouse C'.
```
function catAndMouse(x, y, z) {

}
```
Now, we need to see which cat is further away from the mouse. It's important to remember that we're thinking about distance here, and not money for example.

For that reason, it doesn't really matter if our cat is on a negative position on the number line or a positive position.

All that matters is how many "places"
on the number line our cat is away from the mouse.

Let's look at an example:

> CatA(3) - Mouse(1) = 2

Whereas:
>CatB(-100) - Mouse(1) = -101

Obviously CatA is closer to the mouse and will catch it far before CatB. CatA is only 2 "steps" in the positive direction away from the mouse while CatB is 101 "steps" away in the negative direction.

However, let's change the numbers a bit:
>CatA[50] - mouse(-100) = 150

versus
>CatB(-99) - mouse(-100) = 1

In this scenario CatA is 150 "steps" away from the mouse while CatB is only 1 "step" away from the mouse.

As you can see, it doesn't matter whether our cats are sitting a given number of steps away in the "positive" direction or the "negative" direction.

Far more vital is the absolute number of steps away from the mouse that they are.

For that reason, and because we do not know if either or both of our cats will be starting at a negative position, we need to find the absolute value of the distance between *x-z* and *y-z*. We can do that using the Math.abs() method.

And here's our final solution!
```
function catAndMouse(x, y, z) {
if (Math.abs(x-z) > Math.abs(y-z)) {
  return ("Cat B")
}
else if (Math.abs(x-z) < Math.abs(y-z)) {
  return ("Cat A")
}
else if (Math.abs(x-z) === Math.abs(y-z)) {
  return ('Mouse C')
}
else {
  return ("error: unexpected input")
}
}
```
If the distance between CatA and the mouse is greater than CatB and the mouse, we return "Cat B".

If the distance between CatA and the mouse is less than the distance between CatB and the mouse, we return "Cat A".

If the distances are the same, we return "Mouse C".

And in any other situation, we return "error: unexpected input".

There we go, a comprehensive explanation of this algorithm. Hopefully breaking things down helped you understand! :D

19:20 -- Finished commiting that solution to GitHub.

19:23 -- I've gotten in 4 hours of coding so I will finally give myself permission to eat O_O. When I come back I'll work on the Counting Valleys algorithm on HackerRank(https://www.hackerrank.com/challenges/counting-valleys/problem).

19:24 -- P.S. I currently have 161 points on HackerRank and my global rank is now 447,529.
___
**Total time spent coding today**: 

**Total time spent coding thus far in June 2019**: 

**Total lifetime hours of coding**: 