# Wednesday June 19th, 2019 Daily Coding Journal

9:37 -- Looks like we're not getting a particularly early start today. I can't complain though, the last 2 days I've gotten almost 12.5 hours of coding in!

I'm going to shoot for another 6 hours of coding today. It's a tough target, but one I feel super proud when I actually hit it.

In any case, let't begin!

9:38 -- I currently have 296 points on HackerRank which is good enough for a global rank of 272,397. Let's go and solve the Birthday Chocolate algorithm!

9:40 -- It looks like in this problem we have a girl named Lily who wants to share a chocolate bar with Ron for his birthday.

The chocolate bar has numbers printed on each of its squares. Lily wants to take consecutive squares from the chocolate bar that sum up to be Ron's birthday, and that have a length property (think how many total pieces) equal to Ron's birth month.

I'm going to work on solving this problem, I'll document my progress along the way, and then I'll explain my solution after solving this algorithm.

9:49 -- Initial problem setup:
```
function birthday(s, d, m) {

}
```
9:55 -- Baby steps...
```
function birthday(s, d, m) {
for (let i = 0; i < s.length; i++) {
  console.log(`current is ${s[i]} and previous is ${s[i-1]}`)
}
}
```
9:59 -- Taking a quick break. Back shortly.

10:26 -- I'm back. Let's finish solving this problem.

10:30 -- I'm feeling so confused. I think I'm going to delete everything and start from scratch.

10:31 -- Let's try to write pseudocode, to break things down and make this problem more manageable.

10:39 -- Here's my pseudocode:
```
// initialize approvedGroups variable to empty array.
// initialize counter variable to 0
// initialize currentGroup variable to an empty array
// loop through all of the numbers in *s* array
// update currentGroup variable to an empty array
// push s[i] to currentGroup variable
// set counter equal to s[i]
// use a nested for loop.
// Nested for loop increments counter by s[ii]
// s[ii] is pushed to current group
// break out of nested for loop.
// If counter equals *d* and currentGroup[0].length equals m, push currentGroup[0] to approvedGroups
// repeat??
```
It was starting to get a bit obscure by the end, but let me try to implement it and if anything is off it'll then be easier to see :)

10:48 -- It's coming along...
```
function birthday(s, d, m) {
let approvedGroups = [];
let currentGroup = [];
let counter = 0;

for (let i = 0; i < s.length; i++) {
  currentGroup = [];
  currentGroup.push(s[i])
  counter = s[i];
 for (let ii = i + 1; ii < s.length && currentGroup.length < m; ii++) {
   console.log(s[ii])
 }
}
}
```

10:54 -- I finally solved this algorithm. Here's my final solution:
```
function birthday(s, d, m) {
let approvedGroupCount = 0;
let currentGroup = [];
let counter = 0;

for (let i = 0; i < s.length; i++) {
  currentGroup = [];
  currentGroup.push(s[i])
  counter = s[i];
 for (let ii = i + 1; ii < s.length && currentGroup.length < m; ii++) {
   counter+=s[ii];
   currentGroup.push(s[ii])
 }
 console.log(counter)
 console.log(currentGroup)
 if (counter === d && currentGroup.length === m) {
   approvedGroupCount+=1
 }
}
return approvedGroupCount
}
```
I can't believe this problem was only worth 10 points. It was quite a handful haha. 

UPDATE: I knew my solution wasn't optimized, so I asked myself how I could optimize things. Follow my explanation below for my improved solution that builds off the initial solution.


10:58 -- Let's explain this algorithm step-by-step. To start, we have a function *birthday* which has three parameters *s*, *d*, and *m*.

*s* is an array of integers representing the numbers printed on our squares of chocolate.

*d* is an integer representing Ron's birthday (which the sum of our chocolates must equal).

*m* is an integer representing Ron's birth month (which the length property of our result or "number of chocolates given" must match).
```
function birthday(s, d, m) {

}
```
11:01 -- Moving forward, I've also created a few variables. *approvedGroupCount* initialized to 0, *currentGroup* initialized to an empty array, and *counter* initialized to 0.
```
function birthday(s, d, m) {
let approvedGroupCount = 0;
let currentGroup = [];
let counter = 0;
}
```
11:05 -- Next, we use a for loop to loop through all of the values in our *s* array as long as (s.length - i ) is greater than or equal to m.

This piece of logic is important because it prevents unnecessary looping after we no longer have enough chocolate squares left to satisfy Lily's desire of giving Ron a number of chocolate squares equal to his birth month.

We also reset our current group to an empty array, push the value of *s[i]* to *currentGroup* and set *counter* equal to *s[i]*.

Some of these steps may seem unnecessary now, however, that's simply because we haven't yet implemented our nested for loop.
```
function birthday(s, d, m) {
let approvedGroupCount = 0;
let currentGroup = [];
let counter = 0;

for (let i = 0; i < s.length && (s.length - i) >= m ; i++) {
  currentGroup = [];
  currentGroup.push(s[i])
  counter = s[i];
```
11:10 -- Now, time for the nested for loop. Our nested for loop will start at the chocolate bar after the current bar (let ii = i + 1), and will continue to run as long as we still have chocolate bars (ii < s.length) AND the number of chocolate bars we currently have (the ones we're considering giving to Ron) is less than Ron's birth month ((currentGroup.length < m)), with *ii* being incremented by one each time through the loop.

With each iteration of the loop, we'll increment counter by *s[ii]* and push *s[ii]* to our *currentGroup* array.
```
function birthday(s, d, m) {
let approvedGroupCount = 0;
let currentGroup = [];
let counter = 0;

for (let i = 0; i < s.length && (s.length - i) >= m ; i++) {
  currentGroup = [];
  currentGroup.push(s[i])
  counter = s[i];
 for (let ii = i + 1; ii < s.length && currentGroup.length < m; ii++) {
   counter+=s[ii];
   currentGroup.push(s[ii])
 }
}
```
11:18 -- Finally, after we break out of our nested for loop, we'll evaluate whether *counter* is equal to *d*, and *currentGroup.length* is equal to m.

If so, we know that the given combination of chocolate bars is valid, and we increment *approvedGroupCount* by one.

After that, we'll go back to our previous loops and repeat the process. After all of our looping has eventually finished, we'll return *approvedGroupCount* as our solution to this algorithm.
```
function birthday(s, d, m) {
let approvedGroupCount = 0;
let currentGroup = [];
let counter = 0;

for (let i = 0; i < s.length && (s.length - i) >= m ; i++) {
  currentGroup = [];
  currentGroup.push(s[i])
  counter = s[i];
 for (let ii = i + 1; ii < s.length && currentGroup.length < m; ii++) {
   counter+=s[ii];
   currentGroup.push(s[ii])
 }
 if (counter === d && currentGroup.length === m) {
   approvedGroupCount+=1
 }
}
return approvedGroupCount
}
```
Wow, that was a dense explanation! Well done for following along! :D

11:25 -- Finally got the birthday chocolate algorithm out of the way. I now have 306 points on HackerRank which is good enough for a global rank of 264,145.

11:27 -- In my next coding session I'll tackle the [Jumping on the Clouds: Revisited](https://www.hackerrank.com/challenges/jumping-on-the-clouds-revisited/problem) algorithm.
___
12:22 -- Went through my morning routine, did some house work, now let's work on the next challenge!

12:24 -- We've got a girl named Aerith who is playing a cloud hopping game. Her character's energy starts at 100. It looks like it takes 1 unit of energy to jump from cloud to cloud. But, if her character lands on a thundercloud her character will lose an additional two units of energy.

Our job is to figure out how much energy Aerith will have after all of her jumps.

As usual, I'll document my progress as I go about solving this algorithm, and explain everything in more detail after I reach a final solution.

12:33 -- initial setup:
```
function jumpingOnClouds(c, k) {
console.log(c, k)
}
``` 

12:37 -- A little progress...
```
function jumpingOnClouds(c, k) {
  let energy = 100;
for (let i = 0; i < c.length; i+=k) {
  console.log(c[i])
}
}
```

12:39 -- Wow, I'm finished already:
```
function jumpingOnClouds(c, k) {
  let energy = 100;
for (let i = 0; i < c.length; i+=k) {
  if (c[i] === 1) {
    energy-=3
  }
  else {
    energy -=1
  }
}
return energy
}
```
12:40 -- First, we have a function *jumpingOnClouds* that has two parameters: *c*: an array of integers representing the different cloud types, and *k*: an integer representing the length of one jump.

I've also initialized a variable *energy* to 100, because our character energy starts at 100 per the algorithm instructions.
```
function jumpingOnClouds(c, k) {
  let energy = 100;
}
```
12:44 -- Next, we use a for loop to iterate through our array of clouds *c*. We continue as long as our incrementor *i* is less than the length of our clouds array, also keeping in mind that we're incrementing *i* by the value of *k* or how far our character is capable of jumping.

For each iteration of our array, we identify whether our character landed on a thundercloud (1) or a safe cloud (0). We do this by seeing whether the current array item c[i] is equal to 1.

If so, we know our character landed on a thundercloud and we decrement *energy* by three. Otherwise, we only decrement *energy* by one because we know we're simply dealing with a standard jump onto a normal or safe cloud.

After we've iterated through the entire array and break out of our loop, we return *energy* as our solution to this algorithm!
```
function jumpingOnClouds(c, k) {
  let energy = 100;
for (let i = 0; i < c.length; i+=k) {
  if (c[i] === 1) {
    energy-=3
  }
  else {
    energy -=1
  }
}
return energy
}
```
12:57 -- We made pretty quick work of that last algorithm. I now have 321 points on HackerRank which is good enough for a global rank of 252,914.

12:58 -- In my next coding session I'll solve the [Find Digits](https://www.hackerrank.com/challenges/find-digits/problem) algorithm.
___
13:52 -- Just put my clothes into the wash and cleaned one of the pantry shelves in my parents' house (including sorting out all the expired stuff) to surprise my mom when she comes home.

13:53 -- Anyway, on to the next algorithm!

13:55 -- It looks like we're taking a number and seeing how many of its individual digits its divisble by.

Seems pretty self-explantory to me. I'll document my progress as I work to solve it, then I'll explain my solution after I finish.

14:05 -- Mother was totally ungrateful. Did not say thank you and was more annoyed than anything else with my help.

I will retreat back into the world of code, where a right is a right, and is always recognized as such.

14:15 -- Getting close...
```
function findDigits(n) {
let divisorCount = 0;
let dividend = n;
let divisors;
divisors = String(n).split("");
console.log(divisors)
for (let i = 0; i < n; i++) {
}
}
```
14:21 -- Anyway, I've solved the algorithm. Here's the solution:
```
function findDigits(n) {
let divisorCount = 0;
let dividend = n;
let divisors;
divisors = String(n).split("");
for (let i = 0; i < divisors.length; i++) {
  if (dividend % divisors[i] === 0) {
    divisorCount+=1
  }
}
return divisorCount
}
```
14:22 -- I'm going to take a quick break 15 minutes or so to get my clothes out of the dryer and put them away. Then I'll explain my solution.

14:44 -- We have a function *findDigits* that has a single parameter *n* which takes in an integer that represents the number we will perform division operations on.

I've also declared a few other variables: *divisorCount*: initialized to 0, *dividend* initialized to the value passed to *n*, and *divisors* initialized to the value of String(n).split("").

In other words, divisors will be set to the value of an array in which each item is an individual character taken from the integer passed to *n*.
```
function findDigits(n) {
let divisorCount = 0;
let dividend = n;
let divisors = String(n).split("");
}
```
14:56 -- Next, we'll use a for loop to go through each value in our *divisors* array. Then we have the logic that if our dividend is divisible by our divisor (*divisors[i]) without a remainder, we'll increment divisorCount by 1.

After we finishing iterating through our array we'll break out of our loop and return our variable *divisorCount* as our solution to this algorithm!
```
function findDigits(n) {
let divisorCount = 0;
let dividend = n;
let divisors = String(n).split("");
for (let i = 0; i < divisors.length; i++) {
  if (dividend % Number(divisors[i]) === 0) {
    divisorCount+=1
  }
}
return divisorCount
}
```
Nice job!

15:03 -- I've finished committing the 'Find Digits' algorithm to GitHub. I now have 346 points on HackerRank which is good enough for a global rank of 235,720.

15:06 -- In my next coding session I'll solve the [Cut the sticks](https://www.hackerrank.com/challenges/cut-the-sticks/problem) algorithm.
___
16:38 -- I'm back. I'm going to start working on the Cut the Sticks algorithm.

16:40 -- Here's what we're working with. We have a number of sticks. Our job is to take the length of the shortest stick, and subtract that number from all of our sticks. 

Then we repeat the same process until we're left with nothing.

Before each cut, we should note how many sticks we still have left.

As usual, I'm going to solve this algorithm, document my progress, and then explain everything in more detail after I've solved it.

16:48 -- Basic setup...
```
function cutTheSticks(arr) {
  let numberOfSticks = [];
  let smallestStick = arr[0];
  for (let i = 0; i < arr.length; i++) {
    console.log(smallestStick)
  }
}
```
16:57 -- Current progress... Feeling a bit confused:
```
function cutTheSticks(arr) {
  let numberOfSticks = [];
  let smallestStick = Infinity;
  for (let i = 0; i < arr.length; i++) {
    for (let ii = 0; ii < arr.length; ii++) {
    if (arr[i] < smallestStick) {
      smallestStick = arr[i]
    }
    }
      console.log(smallestStick)
  }
}
```
17:13 -- Things were starting to get reeeealy messy:
```
function cutTheSticks(arr) {
  let numberOfSticks = [];
  let smallestStick = Infinity;
  for (let i = 0; i < arr.length; i++) {
    smallestStick = Infinity;
    numberOfSticks.push(arr.length)
console.log("im the first loop")
console.log(smallestStick)
    for (let ii = 0; ii < arr.length; ii++) {
    if (arr[ii] < smallestStick) {
      smallestStick = arr[ii]
    }
    console.log(`im the second loop + arr[ii] is ${arr[ii]}`)
    }
for (let j = 0; j < arr.length; j++) {
  arr[j]-=smallestStick
  console.log("im the third loop")
}
  console.log(arr)
  }
}
```
Then I realized something important:
>if the value of our sticks is 0 we need to remove them from our array. Of course, instead of removing items from an array, it may be more simple to create a remainingSticks array, and simply not to push any "0 sticks" to that array.

17:24 -- Such a headache trying to solve this problem...

15:32 -- I've solved the algorithm. Here's my not-so-perfect solution:
```
function cutTheSticks(arr) {
  let numberOfSticks = [arr.length];
  let smallestStick = Infinity;
  let remainingSticks = []
  for (let i = 0; i < arr.length; i++) {
    smallestStick = Infinity;

    for (let ii = 0; ii < arr.length; ii++) {
      if (arr[ii] < smallestStick && arr[ii] > 0) {
        smallestStick = arr[ii]
      }
    }
  
  for (let j = 0; j < arr.length; j++) {
    arr[j]-= smallestStick
    if (arr[j] > 0) {
      remainingSticks.push(arr[j])
    } 
  }
    if (remainingSticks.length > 0) {
    numberOfSticks.push(remainingSticks.length)
    }
        remainingSticks = []
  }
  return (numberOfSticks)
}
```
While my solution works, I think that you  could probably solve this algorithm in a more efficient manner.

17:34 -- Regardless, I'm feeling pretty burnt at this point. I'm going to take a break for dinner, and I'll explain my solution when I get back.
___

18:51 -- I had dinner, juggled clubs for 25 minutes, now I'm back! Let's go over the last algorithm.

18:53 -- We have a function *cutTheSticks* which has a single parameter *arr* which takes in an array of integers representing the lengths of our various sticks.

I've also defined a few additional variables *numberOfSticks*: initialized to the length of *arr*, *smallestStick*: initialized to **Infinity**. and *remainingSticks*: initialized to an empty array.
```
function cutTheSticks(arr) {
  let numberOfSticks = [arr.length];
  let smallestStick = Infinity;
  let remainingSticks = [];
}
```
18:58 -- Next, we use a for loop to iterate through all of the items in our array.

Within our first for loop we're going to update the value of *smallestStick* to **Infinity**.

While this may seem somewhat redundant at this point (*smallestStick* was already set to the value of **Infinity** after all), you'll see later on why this step was necessary.
```
function cutTheSticks(arr) {
  let numberOfSticks = [arr.length];
  let smallestStick = Infinity;
  let remainingSticks = [];
  for (let i = 0; i < arr.length; i++) {
    smallestStick = Infinity;
  }
}
```
19:04 -- We've still got quite a ways to go. Now, we're going to create a second for loop.

This nested for loop will be used for determining the smallest stick in our array that *DOES NOT* have a value of 0.

Once we find a value of *arr[ii]* that is smaller than *smallestStick*, which if there are any positive integer values left in our array, they will be larger than *smallestStick* because *smallestStick* was just set to **Infinity** in the previous step, we'll then update *smallestStick* to the value of *arr[ii]*.

That was a loooong sentence, maybe it'll be more simple to just show you the code:
```
function cutTheSticks(arr) {
  let numberOfSticks = [arr.length];
  let smallestStick = Infinity;
  let remainingSticks = [];
  for (let i = 0; i < arr.length; i++) {
    smallestStick = Infinity;

    for (let ii = 0; ii < arr.length; ii++) {
      if (arr[ii] < smallestStick && arr[ii] > 0) {
        smallestStick = arr[ii]
      }
    }
  }
}
```
19:11 -- Now, we're going to need a third loop. Our final loop will iterate through our array, subtracting the value of *smallestStick* from each of our array items.

Then, if a given array item's value is larger than 0, we'll push that array item to *remainingSticks*.

After breaking out of our final loop, we have a conditional statement that says,
> if the length of our *remainingSticks* array is greater than 0, we'll push the length of *remainingSticks* to *numberofSticks*, update the value of *remainingSticks* to an empty array (and then continue through our various loops once again).

Otherwise, we'll return *numberOfSticks* as our solution to this algorithm!

```
function cutTheSticks(arr) {
  let numberOfSticks = [arr.length];
  let smallestStick = Infinity;
  let remainingSticks = [];
  for (let i = 0; i < arr.length; i++) {
    smallestStick = Infinity;

    for (let ii = 0; ii < arr.length; ii++) {
      if (arr[ii] < smallestStick && arr[ii] > 0) {
        smallestStick = arr[ii]
      }
    }
  for (let j = 0; j < arr.length; j++) {
    arr[j]-= smallestStick
    if (arr[j] > 0) {
      remainingSticks.push(arr[j])
    } 
  }
    if (remainingSticks.length > 0) {
    numberOfSticks.push(remainingSticks.length)
    }
    else {
      return (numberOfSticks)
    }
        remainingSticks = []
  }
}
```
19:24 -- If you were reading carefully, you may have noticed that my solution to the algorithm evolved as I was explaining it.

My algorithm is now more efficient because I changed some of the logic at the end. After our final loop my code is now written as:
```
    if (remainingSticks.length > 0) {
    numberOfSticks.push(remainingSticks.length)
    }
    else {
      return (numberOfSticks)
    }
        remainingSticks = []
  }
}
```
This is significantly more efficient than the code I'd written before because now when we no longer have sticks remaining we can simply return *numberOfSticks* as our solution and break out of our function.

This has the potential to save countless unnecessary iterations of our array and greatly improves the performance of our function when it is called!

19:29 -- I just finished commiting the 'Cut the sticks' algorithm solution to [my HackerRank GitHub repo](https://github.com/camchardukian/hackerrank-algorithms).

19:31 -- I now have 371 points on HackerRank which is good enough for a global rank of 220,809.

19:32 -- During my next coding session, I'll work on the [Jumping on the Clouds](https://www.hackerrank.com/challenges/jumping-on-the-clouds/problem) algorithm.

19:34 -- Let's commit this journal entry to GitHub, stretch, and give my eyes a little well-deserved rest!
___
20:52 -- Made a green smoothie, went to the bathroom, talked to my brother on the phone a little, got some exercise in.

That's how the last hour or so went. Now, it's time for the next algorithm.

20:56 -- It looks like we have a girl named Emma who is playing a video game where there are consecutively numbered clouds.

Emma's character can jump either 1 or 2 clouds beyond the cloud she is currently standing on.

We have to find the minimum numbers of jumps required for Emma's character to make it from her starting position to the final cloud.

According to the algorithm's instructions, it is always possible to win the game.

21:00 -- I'm going to solve this algorithm while documenting my progress along the way. When I reach my final solution, I'll guide you along my way of thinking and help you understand how I came to that conclusion.

21:05 -- Initial setup:
```
function jumpingOnClouds(c) {
console.log(c)
}
```
21:16 -- I'm a little bit surprised, but it looks like I've found a solution already:
```
function jumpingOnClouds(c) {
  let jumpCount = 0;
for (let i = 0; i <= c.length -2;) {
  if (c[i + 2] === 1) {
    i+=1
  }
  else {
    i+=2
  }
  jumpCount+=1
  console.log(i)
}
return jumpCount
}
```
Let me explain.

21:17 -- We have a function *jumpingOnClouds* that has a single parameter *c* which takes in an array of integers that represent cloud types that are either safe (0) or must be avoided (1).

I've also initialized another variable *jumpCount* to 0.
```
function jumpingOnClouds(c) {
  let jumpCount = 0;
for (let i = 0; i <= c.length -2;) {
  if (c[i + 2] === 1) {
    i+=1
  }
  else {
    i+=2
  }
  jumpCount+=1
  console.log(i)
}
return jumpCount
}
```
21:21 -- Moving forward, I've created a for loop that starts at 0, and continues for as long as our variable *i* is less than or equal to the length of our *c* array minus two.

*Why (c.length - 2)?* Because we want our character to continue jumping all the way to the end of our array of clouds. We subtract 2 in this case, because the greatest length our character is capable of jumping is 2 clouds.

Also, notice that I didn't utilize the third optional expression in our for loop.

While normally we would increment *i* at this point, in this case, doing so is not necessary because we will increment *i* within the loop itself.

More on that later...
```
function jumpingOnClouds(c) {
  let jumpCount = 0;
for (let i = 0; i <= c.length -2;) {
    }
}
```
21:27 -- Are you still following along? Hopefully I haven't lost you yet ;) Anyway, within our for loop, we'll create an expression that states:
> If c[i+2] equals 1, we'll only increment *i* by one. This is because we know that if our character jumps two clouds forward (c[i+2]), that our character would jump onto a cloud that isn't safe to jump on. Thus, we only increment *i* by one because we only want our character to jump one cloud forward.

If on the other hand, c[i+2] **DID NOT** equal 1, we'd know that our character would be safe in jumping two clouds forward. Thus, we'd have no problem incrementing *i* by two.

Regardless of whether we increment *i* by one or two, we should increment *jumpCount* by one because we know our character just took another jump forward.

As long as our character has yet to reach the final cloud, we'll continue to loop through this process incrementing *i* by one or two.

Eventually, however, we'll reach the final cloud and break out of this loop. When that happens, we can return *jumpCount* as our solution to this algorithm!
```
function jumpingOnClouds(c) {
  let jumpCount = 0;
for (let i = 0; i <= c.length -2;) {
  if (c[i + 2] === 1) {
    i+=1
  }
  else {
    i+=2
  }
  jumpCount+=1
}
return jumpCount
}
```
Nice work!

21:43 -- Almost hit 6 hours of coding... Going to take a break now. In my final coding session later tonight, I'll work to solve the [Minimum Distances](https://www.hackerrank.com/challenges/minimum-distances/problem) algorithm.
___
22:39 -- One. More. Coding. Session. I. Can. Do. It.

22:40 -- I'm working on the 'Minimum Distances' algorithm now. It seems pretty simple. We're given an array of integers and our job is to find any matching pair of integers (for example, 3 & 3 or 11 & 11).

If there are multiple pairs of matching integers, we return the distance between the matching pair that is closest together.

If there is only one pair of matching integers, we simply return the distance between the pair.

If there are no pairs of matching integers, we just return -1.

22:43 -- I don't expect this algorithm to take more than 10-15 minutes to solve. But who knows, maybe I'll jinx my progress by predicting it ;)

In any case, I'll solve the algorithm, document my progress, and explain my solution afterwards.

22:46 -- Initial setup:
```
function minimumDistances(a) {

}
```
22:53 -- Feeling a little confused now...
```
function minimumDistances(a) {

for (let i = 0; i < a.length; i++) {
  for (let ii = 0; a[ii] !== a[i] && ii < a.length; ii++) {
    console.log(`a[i] is: ${a[i]} and a[ii] is: ${a[ii]}`)
  }
}
}
```
23:03 -- Straightening things out...
```
function minimumDistances(a) {

for (let i = 0; i < a.length; i++) {
  for (let ii = i+1; [ii] < a.length+1 ; ii++) {
    if (a[i] === a[ii]) {
      console.log("pair")
    }
  }
}
}
```
23:05 -- My *pairsArray* has the pairs I need, but now I have to loop through my *pairsArray* and do some subtracting...
```
function minimumDistances(a) {
let pairsArray = [];

for (let i = 0; i < a.length; i++) {
  for (let ii = i+1; [ii] < a.length+1 ; ii++) {
    if (a[i] === a[ii]) {
      pairsArray.push([i, ii])
    }
  }
}
console.log(pairsArray)
}
```
23:17 -- Man I really did jinx things lol. This one looked simply but took me quite a bit longer than I expected. On the bright side, I'm finished now. Here's my solution for this algorithm:
```
function minimumDistances(a) {
let pairsArray = [];
let minimumDistance = Infinity;
let result;

for (let i = 0; i < a.length; i++) {
  for (let ii = i+1; [ii] < a.length+1 ; ii++) {
    if (a[i] === a[ii]) {
      pairsArray.push([i, ii])
    }
  }
}
if (pairsArray) {
for (let i = 0; i < pairsArray.length; i++) {
  if ((pairsArray[i][1]) - pairsArray[i][0] < minimumDistance) {
    minimumDistance = pairsArray[i][1] - pairsArray[i][0]
  }
}
}
minimumDistance < Infinity ? result = minimumDistance : result = -1

return result
}
```
23:18 -- I'm well over my daily challenge of 6 hours of daily coding already. That along with feeling pretty burnt and my wrists starting to get sore means it's time to call it a day!

I'll explain this algorithm's solution tomorrow.

For now, I'm going to tally up my coding hours, commit this journal entry to GitHub, and then record a video for the [Daily Developer show](https://www.youtube.com/channel/UCRUPCpCWCL6Mr-0QWNje29Q).

___
**Total time spent coding today**: 6 hours 30 minutes

**Total time spent coding thus far in June 2019**: 44 hours 52 minutes

**Total lifetime hours of coding**: 616 hours 35 minutes