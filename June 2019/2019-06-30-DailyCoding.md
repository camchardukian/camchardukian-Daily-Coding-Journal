# Sunday June 30th, 2019 Daily Coding Journal

7:14 -- I'm up. I made myself get early because I have a family event I need to attend today. However, yesterday I didn't get much programming time in.

Thus today, getting some coding time in needs to be prioritized before anything else.

7:17 -- It looks like we have a boy named Marc that loves to eat cupcakes. Apparently, however, Marc also likes to stay fit. Go figure.

Marc is going to eat a number of cupcakes. Afterwards, he must walk a certain number of miles to burn off each cupcake.

The first cupcake he must walk off the number of calories times 2^0 (0th power). The second cupcake he must walk off the number of calories times 2^1. The third cupcake he must walk off the number of calories times 2^2 and so on.

Our job is to determine the optimal order in which Marc should eat his cupcakes.

We will do this using the functions *marcsCakewalk* and its parameter *calorie*, which is an array of integers representing the calorie count for each cupcake.

Here's our basic setup:
```
function marcsCakewalk(calorie) {

}
```
7:23 -- As usual, I'll solve this problem documenting my progress along the way. When I reach my final solution, I'll explain it to you.

7:29 -- Here's some pseduocode I've written to plan my solution:
```
// sort our calorie array from largest integer to smallest integer.

// Multiply the first item in our array (the largest integer found after sorting) by 2^0, the second item by 2^1, the third item by 2^2, and so on.

// Add up the results from all of the multiplying in the previous step and return that as our solution to this algorithm!
```
7:33 -- Began implementing my solution...
```
function marcsCakewalk(calorie) {
calorie = calorie.sort((a, b) =>{
  return b - a
})
console.log(calorie)
}
```
7:41 -- Here's my final solution:
```
function marcsCakewalk(calorie)
 {
let necessaryMiles = 0;
calorie = calorie.sort((a, b) =>{
  return b - a
})
for (let i = 0; i < calorie.length; i++) {
necessaryMiles += Math.pow(2, i)* calorie[i]
}
return necessaryMiles
}
```
Let's go over how it all works...

7:41 -- After we get our basic function setup, we need to do two things. The first thing is declare a variable *necessaryMiles*.

We'll later use this variable to keep a tally of how many total miles Marco will need to walk as he eats the cupcakes in his array *calories*.

The other thing we need to do is sort our array *calories*. *Why?* Because for whatever reason Marco's digestive system processes the first cupcake he eats very efficiently:
> Amount of walking equals *insertCupcakeCalorieCountHere* times 2^0.

Later cupcakes, however, are digested much less efficiently. 2^1, 2^2, 2^100... you get the idea.

For that reason, we want Marco to eat the largest cupcakes first. This will minimize the total amount of miles he will later need to walk.

We can sort our array *calorie* by using the sort method, and passing it a callback function *return b - a* that will return all of the integers in our array from the largest positive value, to 0, to any hypothetical negative values.
```
function marcsCakewalk(calorie)
 {
let necessaryMiles = 0;
calorie = calorie.sort((a, b) =>{
  return b - a
    })
}
```
7:55 -- Now that we have our array sorted from largest to smallest integer, or largest cupcake to smallest cupcake, we now need to calculate how many miles Marco will have to walk as a result of eating each cupcake.

We can do this by using a for loop and going through each number in our array *calorie* using the equation defined to us in this algorithm's instructions.

We'll declare and initialize our variable *i* to **0**.

We'll have 2^i times calorie[i]. We'll then increment our variable *necessaryMiles* by the result of that last equation.

Then, we'll increment *i* by 1, and repeat the process for the second item, third, fourth, and so on items in our array *calorie*.

After we finish looping through all of the items in our array, incrementing *necessaryMiles* each time through our loop, we'll eventually break out of our loop when *i* is greater than the length of our array *calorie* (and thus there are no more cupcakes).

When that happens, we can return *necessaryMiles* as our solution to this algorithm!
```
function marcsCakewalk(calorie) {
    let necessaryMiles = 0;
    calorie = calorie.sort((a, b) => {
  return b - a
    })
    for (let i = 0; i < calorie.length; i++) {
    necessaryMiles += Math.pow(2, i)* calorie[i]
    }
    return necessaryMiles
}
```
8:06 -- Way to stick with it. You made it all the way through the algorithm!

8:14 -- I just finished commiting the Marc's cupcakes algorithm to GitHub.

8:15 -- I now have 778.5 points, which is good enough for a rank of 100,445 on HackerRank's global algorithm leaderboard.

8:16 -- Although it has a relatively low successful completion percentage (78%), during my next coding session I'll attempt to solve the [Save the Prisoner!](https://www.hackerrank.com/challenges/save-the-prisoner/problem) algorithm.
___
16:38 -- Since the last journal entry I was able to get a couple hours of sleep in, go through my morning routine, and also head to the annual Armenian picnic in my hometown.

With all of that out of the way, let's start working on solving the next algorithm!

16:41 -- It looks like we're hanging out at a jail that has a number of prisoners. We're handing out candy to the prisoners in order from smallest to largest (1 to 4).

If there are any additional candies remaining after prisoner #4 receives a candy, we'll repeat the process.

Here's the catch... Sometimes prisoner #1 will not be the first person to receive candy.

If the prison guard draws the number 3 out of his hat for example, prisoner #3 would be the first to draw candy.

Oh, and one more thing. The last person to receive candy will receive a "fake" candy that tastes horrible.

Our job is to determine which prisoner will receive the fake candy.

To do so, we have a function *saveThePrisoner* to help us. This function has several parameters including:
* *n*: an integer representing the number of prisoners.
* *m*: an integer representing the number of candies.
* *s*: an integer representing the chair number to begin passing sweets out at.

Here's our basic setup:
```
function saveThePrisoner(n, m, s) {

}
```
16:47 -- As usual, I'll work to solve this algorithm, documenting my progress along the way. After I reach a final solution, I'll walk you through how I reached my solution and aim to help you understand how a developer may think about solving this problem. :)

Let's go!

16:52 -- Here's some very basic conceptual thinking and pseduocode:
```
// Determine how many prisoners there are.

// Figure out which prisoner we'll start handing our candy out at.

// Loop through our list of prisoners decrementing our remainingCandies variable by one each time our loop runs.

// Return our current prisoner as our solution to this algorithm.
```
16:57 -- One issue I'm having is that I'm not sure how I can iterate over my array of prisoners multiple times...

I suppose I could just use an if statement to update the value of *i* if necessary.

17:00 -- Here we go. Making progress:
```
function saveThePrisoner(n, m, s) {
let remainingCandies = m;

for (let i = 1; i <= n; i++) {
  console.log(`I am the ${i} prisoner`)
  if (i === 4) {
  i = 0;
  }
 }
}
```
17:15 -- I've created a solution that works for small numbers:
```
function saveThePrisoner(n, m, s) {
let remainingCandies = m;

for (let i = s; i <= n; i++) {
remainingCandies -=1
  if (remainingCandies === 0) {
    return i
  }
  if (i === n) {
  i = 0;
  }
 }
}
```
17:16 -- Unfortunately, I'm having issues with some of the user tests on HackerRank that deal with larger numbers.

Perhaps I need to think of some way to use the modulus operator to process things more efficiently.

17:20 -- I'm going to take a break now and visit with my family before some of them return home.

21:06 -- Exercised for an hour and spent some time with family. Let's get back to coding now.

21:13 -- I've produced a new solution now:
```
function saveThePrisoner(n, m, s) {
let remainingCandies = m;

for (let i = s; i <= n; i++) {
  while (remainingCandies > n) {
    remainingCandies -= n
  }
remainingCandies -=1
  if (remainingCandies === 0) {
    return i
  }
  if (i === n) {
  i = 0;
  }
 }
```
This solution is efficient enough to individually solve one input of large numbers at a time.

When there are 100+ sets of large numbers, however, it seems my current solution is still not efficient enough.

It seems I need to increase my function's efficiency yet again to avoid anything timing out.

21:23 -- Here's some rough pseudocode I wrote while trying to brainstorm a solution that requires less looping:
```
// 1    2     3    $4     5    6     7   8  9
// number of prisoners = 9
// current position = 4
// remaining candies = 6

// if s + remainingCandies is less than the length of our prisoners array, add that value to our current position.

// If s + remainingCandies is MORE than the length of our prisoners array, take number of prisoners - current position, then take the result of that and do (math.abs(result - remainingCandies))
```
21:29 -- Halfway finished with implementing the new solution...
```
function saveThePrisoner(n, m, s) {
let remainingCandies = m;
while (remainingCandies > n) {
    remainingCandies -= n
  }
console.log(`candy count is ${remainingCandies} and position is ${s}`)
  if ((s + remainingCandies) < n) {
    return s + remainingCandies
  }
}
```
Also, a mistake I made in my pseudocode was that we should be more concerned with the value of *n*. *n.length* is irrelevant as we're dealing with an integer and not an array of a specific length.

21:50 -- I have now passed 5 of the 12 test cases with the following solution:
```
function saveThePrisoner(n, m, s) {
    let remainingCandies = m;
    while (remainingCandies > n) {
        remainingCandies -= n
    }
    console.log(`candy count is ${remainingCandies} and position is ${s}`)

    if (remainingCandies === 1) {
        return s
    }
    if ((s + remainingCandies) <= n) {
        return (s + remainingCandies) - 1
    }
    else if ((s + remainingCandies) > n) {
        return Math.abs((n - s) - remainingCandies) - 1
    }
    else {
        return "Error"
    }
}
```
21:55 -- I can't seem to figure out why things aren't working. I'm going to take a break. I think I'll be back for one more coding session later tonight.

I haven't yet decided if I'll give it one more go or not yet. In any case, see you later...
___
23:15 -- Let's give this algorithm one more go. This time, we'll try to handle things using the modulus operator.

23:32 -- Trying to create a different solution from scratch.
```
function saveThePrisoner(n, m, s) {
let leftovers;
let result;
if (m === n) {
  leftovers = 0
}
else if (m > n) {
  leftovers = m % n
}
else {
  leftovers = false;
}
if (leftovers === 0) {
  s - 1 > 0? result = s - 1 : result = n
console.log(result)
}
}
```
23:42 -- A little bit more progress. Just trying to wrap my head around everything...
```
function saveThePrisoner(n, m, s) {
let leftovers;
let result;
if (m === n) {
  leftovers = 0
}
else if (m > n) {
  leftovers = m % n
}
else {
  leftovers = false;
}
if (leftovers === 0) {
  s - 1 > 0? result = s - 1 : result = n
console.log(result)
}
if (leftovers) {
  if ((s + leftovers) <= n) {
    result = (leftovers + s) -1
  }
  console.log('orocess')
}
console.log(result)
}
```
UPDATE: In the end, I wasn't able to solve the algorithm in a satisfactory manner. As a result, I was only able to claim a small percentage of the points available for this algorithm.

Maybe when my skills improve I'll be able to solve the algorithm more effectively and get more points. In any case, I'll see you in tomorrow's journal entry!
___
**Total time spent coding today**: 3 hours 28 minutes

**Total time spent coding in June 2019**: 78 hours 38 minutes

**Total lifetime hours of coding**: 650 hours 20 minutes