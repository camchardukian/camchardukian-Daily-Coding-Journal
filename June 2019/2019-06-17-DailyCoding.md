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
**Total time spent coding today**: 

**Total time spent coding thus far in June 2019**: 

**Total lifetime hours of coding**: 