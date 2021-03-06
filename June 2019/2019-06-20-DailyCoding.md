# Thursday June 20th, 2019 Daily Coding Journal

8:53 -- Yesterday was awesome. We got a ton of development practice. Let's see if we can replicate our strong efforts again today!

8:54 -- We're going to start off with me explaining my solution to the Minimum Distances algorithm from yesterday.

8:58 -- Here's my solution from yesterday:
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
8:59 -- Let's talk about how we got there.

9:00 -- First, we have a function *minimumDistances* that has a single parameter *a* which takes in an array of integers. Our goal is to find the minimum distance between any pair of matching integers (5 & 5 or 19 & 19 for example) our array may have. 

If there are multiple pairs, we'll find the distance for all of them and return the shortest possible distance between any of the pairs.

If there are no pairs of matching integers, we'll simply return -1. Here's our basic setup.

```
function minimumDistances(a) {

}
```
9:03 -- I've also defined a few additional variables: *pairsArray*: initialized to an empty array, *minimumDistance*: initialized to **Infinity**, and *result*: which is declared but not initialized to anything.
```
function minimumDistances(a) {
let pairsArray = [];
let minimumDistance = Infinity;
let result;
}
```
9:07 -- Next, we use a for loop to iterate through each item in the array passed to *a*. We also use a nested for loop to compare each item in our array to every other item in our array.

Plus, within our nested for loop we have an if statement wherein if we detect two matching integers (a[i] === a[ii]), we'll then push the position of those integers to *pairsArray*.

It's important to note that we're only pushing the position of said integers to *pairsArray*, and NOT the integers themselves. This is because this algorithm is interested in finding the distance between matching pairs, but gives no importance to how large or small those matching pairs may be.
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
}
```
9:13 -- Eventually, we'll break out of our two for loops. When that occurs we have another if statement. This if statement basically says, if there is anything in our *pairsArray* do the following logic...

Said logic is a for loop which iterates through each item in *pairsArray*. Then, we ask ourselves:
> If a given item in our array's 1st value minus its "0th" value is less than the current value of *minimumDistance*, we'll then update the value of *minimumDistance* to equal the result of pairsArray[i][1] - pairsArray[i][0].

We'll loop through each item in *pairsArray* using that logic, updating *minimumDistance* as needed before eventually breaking out of our loop.

After doing so we have a ternary operator that says, if minimumDistance is less than **Infinity** (meaning, we must have updated *minimumDistance* at some point and thus our array obviously has some presence of matching integer pairs), we'll set our variable *result* equal to *minimumDistance*.

Otherwise, we'll set *result* equal to -1 (because our array didn't have any matching pairs of integers).

Finally, we'll return *result* as our solution to this algorithm!
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
Way to go!

9:30 -- I now have 411 points which gives me a global rank of 200,466 on HackerRank for algorithms and data structures.

9:31 -- During my next coding session I'll solve the [Drawing Book](https://www.hackerrank.com/challenges/drawing-book/problem) algorithm.
___
10:37 -- Here we go. 2nd coding session of the day.

10:38 -- We have a girl named Brie. Brie has to follow her teacher's direction to open her book to page *p*. Given that the book is *n* pages long, we must determine the minimum number of pages Brie must turn to arrive at *p*.

Here's the catch. Brie can start turning pages from either the front or the back of the book.

10:42 -- I'm going to try to solve this algorithm, while documenting my progress along the way. After I've found a solution, I'll share it with you here and explain how I came to it.

10:44 -- Basic function setup:
```
function pageCount(n, p) {

}
```
10:49 -- Figured out how many page turns from front to back. Now I think I can create a similar for loop to calculate page turns from back to front. Then, I can write a ternary statement to compare the two counts and set my variable *result* to the lesser of the two.
```
function pageCount(n, p) {
let frontToBack = 0;
let backToFront = 0;
let result;
for (let i = 1; i < p; i+=2) {
  frontToBack+=1
}
console.log(frontToBack)
}
```
11:01 -- Getting very close. Passed 26 out of 27 test cases:
```
function pageCount(n, p) {
let frontToBack = 0;
let backToFront = 0;
let result;
for (let i = 1; i < p; i+=2) {
  frontToBack+=1
}
for (let i = n - 1; i > p; i-=2) {
  backToFront+=1
}
frontToBack > backToFront? result = backToFront : result = frontToBack;

return result
}
```
11:30 -- I'm stuck. I'm going to take a break to try to clear my head.
___
11:58 -- I'm back. I'm going to hammer away for a few more minutes before I try switching my approach or starting from scratch.

12:05 -- I wrote this to visualize the different pages of the book:
```
// [1], [2, 3], [4, 5], [6, 7], [8, 9]
```
12:08 -- Being able to visualize things and making religious use of the console.log() method helped me finally solve this algorithm! Here's my final solution (console.logs and all):
```
function pageCount(n, p) {
let frontToBack = 0;
let backToFront = 0;
let result;
for (let i = 1; i < p; i+=2) {
  frontToBack+=1
    console.log(`ftb is ${frontToBack}`)
}
for (let i = n; i > p; i-=2 ) {
  if (i % 2 === 1 && i - 1 === p) {
console.log("arrived")
  }
  else {
    backToFront+=1
  }
    console.log(`btf is ${backToFront}`)
}

frontToBack > backToFront? result = backToFront : result = frontToBack;

return result
}
```
12:09 -- Let's talk about how to solve this algorithm. First, we have a function *pageCount* that has two parameters *n*: an integer representing the total numbers of pages in the book, and *p*: an integer representing the page number the teacher wants Brie to open her book to.

I've also defined a few additional variables: *frontToBack*: initialized to 0, *backToFront*: initialized to 0, and *result*: declared, but not given any initial value.
```
function pageCount(n, p) {
let frontToBack = 0;
let backToFront = 0;
let result;
}
```
12:13 -- Now that we've got the skeleton of our function setup, the next thing we need is a for loop. We're going to use a for loop to count how many pages it would take Brie to reach *p* if she starts at page 1.

Each time we go through our loop, we'll increment *i* by two (because turning the page from 1 doesn't just give us 2, but it gives us 2-3, and then 4-5, then 6-7, and so on).

With that being said we will NOT increment *frontToBack* by two because this variable's intent isn't to count how many total pages we've read or moved past.

This variable's intent is to simply count how many times we touched the bottom right corner of the book to turn the page. For that reason, we're only going to increment *frontToBack* by 1 each time through the loop.
```
function pageCount(n, p) {
let frontToBack = 0;
let backToFront = 0;
let result;
for (let i = 1; i < p; i+=2) {
  frontToBack+=1
 }
}
```
12:18 -- Next, we also need to evaluate how many page turns we would need to reach the desired page if we were starting from the end of the book.

For that reason, we'll create another for loop. This for loop will have have a variable *i* that's initialized to *n* because we want our initial page or starting point to be the end of the book.

We'll continue turning the page as long as *i* is greater than *p*, decrementing i by 2 with each iteration. However, if our *i* is an odd number, and *i* - 1 equals *p*, we'll know that we have arrived to the proper page and no longer need to increment *backToFront*.

Unless the above holds true, we'll increment *backToFront* each time we go through our loop.
```
function pageCount(n, p) {
let frontToBack = 0;
let backToFront = 0;
let result;
for (let i = 1; i < p; i+=2) {
  frontToBack+=1
}
for (let i = n; i > p; i-=2 ) {
  if (i % 2 === 1 && i - 1 === p) {
  }
  else {
    backToFront+=1
  }
 }
}
```
12:26 -- Finally, we will use a ternary operator to set the value of our variable *result*. If *frontToBack* is greater than *backToFront*, we'll set *result* equal to *backToFront* as that would be the method of arriving at page *p* with the fewest number of page turns.

Otherwise, we'll set *result* equal to *frontToBack*.

Regardless of how our ternary operator evaluates, when it is finished evaluating we'll return *result* as our solution to this algorithm!
```
function pageCount(n, p) {
let frontToBack = 0;
let backToFront = 0;
let result;
for (let i = 1; i < p; i+=2) {
  frontToBack+=1
}
for (let i = n; i > p; i-=2 ) {
  if (i % 2 === 1 && i - 1 === p) {
  }
  else {
    backToFront+=1
  }
}

frontToBack > backToFront? result = backToFront : result = frontToBack;

return result
}
```
I can't believe this algorithm was only 10 points. It was a bit of a handful ;). But, if you made it to the end, excellent job on your part!

12:33 -- It's good that we were able to persist and solve that last algorithm. I also think teaching how to solve each algorithm is useful not only as a portfolio piece, but also as a way of forcing myself to defend why I did each thing the way I did.

This helps me to understand why I'm solving a problem in a certain way rather than just hacking things together.

12:35 -- During my next coding session, I'll work to solve the [Service Lane](https://www.hackerrank.com/challenges/service-lane/problem) algorithm.
___
16:10 -- Doing all this programming must be really mentally intensive. Apart from sleeping 6.75 hours last night, my body also just took a 3 hour nap! O_O

But now that we're done with that, let's get back to the grind.

16:12 -- Defining this problem feels a little bit confusing for me. It looks like we have a man named Calvin that is driving on the freeway.

Unfortunately, his check engine light is on and he wants to service his vehicle immediately.

Keeping in mind that the service lane is of varying widths at various points, our job is to help Calvin calculate the maximum size vehicle that can travel through each segment of the service lane safely.

16:21 -- Here's our basic function setup:
```
function serviceLane(n, cases) {

} 
```
16:24 -- I really don't like how this problem is worded. Either I understand the problem and feel they could have phrased things less ambiguously, or I don't understand the problem and I made things too simple in my head.

Anyway, here's where I'm at now.
```
function serviceLane(n, cases) {
console.log(`n is the various widths within the service lane: ${n}`)

console.log(`cases are various test cases where we're trying to pull into the service lane, and we need to see how wide the service lane is thoughout to see the maximum width a vehicle could possibly be for it to be capable of driving through the service lane: ${cases}`)

}
```
16:32 -- Now that we understand the problem a bit more clearly, let's get to work. I'll update you on my progress as I go along. After I finish, I'll explain to you how my solution works.

16:42 -- Quick update...
```
function serviceLane(n, cases) {
for (let i = 0; i < cases.length; i++) {
  for (let ii = cases[i][0]; ii < cases[i][i])
 console.log(`${cases[i][0]} and ${cases[i][1]}`)
 }
}
```
16:45 -- I feel like a shark smelling blood in the water...
```
function serviceLane(n, cases) {
for (let i = 0; i < cases.length; i++) {
  for (let ii = cases[i][0]; ii < cases[i][1]; ii++) {
    console.log(`i equals: ${i} and ii equals: ${ii}`)
  }
 console.log(`${cases[i][0]} and ${cases[i][1]}`)
 }
}
```
16:50 -- Now I just need to figure out if this algorithm wants me to return all of the "answers" into an array, or just log them to the console one by one.

16:53 -- HackerRank has me feeling a bit annoyed. My solution works fine in repl.it, returning *resultsArray* as my answer, and an answer that perfectly matches what HackerRank is asking for.

On HackerRank, however, it's simply logging 'Infinity' to the console, completely ignoring my return statement to return *resultsArray*
```
function serviceLane(n, cases) {
  let minimumWidth = Infinity;
  let resultsArray = []
for (let i = 0; i < cases.length; i++) {
  minimumWidth = Infinity;
  for (let ii = cases[i][0]; ii <= cases[i][1]; ii++) {
    if (n[ii] < minimumWidth) {
      minimumWidth = n[ii]
    }
  }
 resultsArray.push(minimumWidth)
}
return resultsArray
}
```
17:00 -- The only issue I can think of is that perhaps the explanation on HackerRank was unclear and that perhaps the variables I'm receiving are not arrays, but simply a list of integers that I need to convert to an array??

17:06 -- As I suspected, the issue wasn't with my solution but with the test cases themselves. I went to the discussion area and while many commented that this problem was poorly defined (as I said earlier), others commented that the test cases were written incorrectly.

One user shared his modified test cases that would correctly display whether your answer was correct or not. After adopting his test cases, I've now passed the challenge.

HackerRank really does make you work on your problem solving, even going so far as to creating problems with the problems themselves :p.

In any case, my previous solution will pass as expected if you change the main function around line 43 to the following:
```
function main() {
    const ws = fs.createWriteStream(process.env.OUTPUT_PATH)

    const [n, t] = [...readLine().split(' ')].map(x => parseInt(x, 10))
    const width = readLine().split(' ').map(x => parseInt(x, 10))
    const cases = Array(t).fill(0).map(x => readLine().split(' ').map(y => parseInt(y, 10)))
    let result = serviceLane(width, cases)

    ws.write(result.join("\n") + "\n")
    ws.end()
}
```
17:09 -- Wow, that was a good session. I'm going to take a break to exercise, and then I'llexplain my solution during my next coding session.
___
17:50 -- Just got some quality exercise in. Now, let's explain our solution for the last algorithm.

17:51 -- Note: the user tests for this algorithm are a bit problematic. For that reason, around line 43 you need to change the *main* function to the following in order for your tests to pass and yoursolution to be accepted:
```
function main() {
    const ws = fs.createWriteStream(process.env.OUTPUT_PATH)

    const [n, t] = [...readLine().split(' ')].map(x => parseInt(x, 10))
    const width = readLine().split(' ').map(x => parseInt(x, 10))
    const cases = Array(t).fill(0).map(x => readLine().split(' ').map(y => parseInt(y, 10)))
    let result = serviceLane(width, cases)

    ws.write(result.join("\n") + "\n")
    ws.end()
}
```
17:52 -- That small disclaimer aside, let's explain our solution. We have a function *serviceLane* with two parameters *n*: an array of integers representing the various widths within the service lane, and *cases*, a 2-d array of integers representing the various test cases where we're trying to pull into the service lane, and we need to see how wide the service lane is thoughout to see the maximum width a vehicle could possibly be for it to be capable of driving through the service lane.
```
function serviceLane(n, cases) {

}
```
17:57 -- I've also defined a few additional variables: *maxWidth* which is initialized to 0, and represents the maximum possible width a vehicle could be and still drive through all assigned parts of the service lane, and *resultsArray* which is initialized to an empty array and will later be used to hold the results produced from our various test cases.
```
function serviceLane(n, cases) {
  let maxWidth = Infinity;
  let resultsArray = [];
}
```
18:01 -- Next, we're going to use a for loop to iterate through each item in *cases*. Also note, that each time through our array we're going to update the value of *maxWidth* to Infinity.

We're doing this because each time we evaluate a new test case, we want to have a "fresh start" so to speak.

For example, it doesn't matter if a smart car was capable of driving through the previous test case if we're now evaluating a wider portion of the service lane and a school bus could now pass the user tests.
```
function serviceLane(n, cases) {
  let maxWidth = Infinity;
  let resultsArray = [];
for (let i = 0; i < cases.length; i++) {
  maxWidth = Infinity;
 }
}
```
18:05 -- Next, we need a nested for loop. Our nested for loop will iterate between all of the array items in *n* starting at the value of *cases[i][0]* (the first point in a given ordered pair from the *cases* array), and ending at *cases[i][1]* (the second point in a given ordered pair from the *cases* array).

Within this loop, we've added an if statement that says if at any point *n[ii]* is less than *maxWidth*, we'll update the value of *maxWidth* to equal *n[ii]*.

After each iteration of our nested for loop, we'll take the value of *maxWidth* and push it to *resultsArray*.

After we finish pushing, we'll then enter the next cycle of our outer for loop beginning with updating the value of *maxWidth* to **Infinity** and repeating all of the previous steps.

Eventually, after we finish cycling through both of our for loops the necessary amount of times, we'll return *resultsArray* as our solution to this algorithm!
```
function serviceLane(n, cases) {
  let maxWidth = Infinity;
  let resultsArray = [];
for (let i = 0; i < cases.length; i++) {
  maxWidth = Infinity;
  for (let ii = cases[i][0]; ii <= cases[i][1]; ii++) {
    if (n[ii] < maxWidth) {
      maxWidth = n[ii]
    }
  }
 resultsArray.push(maxWidth)
}
return resultsArray
}
```
18:12 -- Remember to view my disclaimer at the top of this file and change your *main* function on HackerRank if your test cases are not passing. Of course, if you're just playing around on repl.it, you won't have to worry about doing anything with *main*.

You're finished. Way to go!

18:18 -- I now have 441 points which is good enough for a rank of 187,506 on HackerRank's algorithms and data structures global leaderboard.

18:19 -- Next, let's start working on the next algorithm. If you're following along, I'm now working on the [Chocolate Feast](https://www.hackerrank.com/challenges/chocolate-feast/problem) algorithm on HackerRank.

18:20 -- It looks like for this problem we have a boy named Bobby that likes going to the discount store to buy chocolates. If Bobby saves up enough wrappers he can exchange them for a free chocolate.

It looks like our goal is to figure out how many chocolate bars Bobby will receive given the following parameters: *n*: an integer representing the amount of money Bobby is starting with, *c*: an integer representing the cost of a chocolate bar, and *m*: an integer representing the number of wrappers Bobby can turn in for a free chocolate bar.

Also note that we're making a few assumptions. The first assumption is that Bobby will use all of his money. The second assumption is that Bobby will immediately turn in his wrappers for a free bar of chocolate if he has enough wrappers.

18:27 -- I'll work to solve this algorithm and update you as I go along. After solving it in its entirety, I'll explain my solution to you.

18:33 -- Getting close to a solution:
```
function chocolateFeast(n, c, m) {
  let chocolateBars = 0;
for (let i = n; i >= 0; i-= c) {
  if (i != n) {
  chocolateBars+=1
  }
}
console.log(chocolateBars)
}
```
18:38 -- Getting very close...
```
function chocolateFeast(n, c, m) {
  let chocolateBars = 0;
for (let i = n; i >= 0; i-= c) {
  if (i != n) {
  chocolateBars+=1
  }
}
chocolateBars+= (Math.floor(chocolateBars/m))
return chocolateBars
 }
```
18:45 -- I've passed 9/11 test cases with this solution:
```
function chocolateFeast(n, c, m) {
  let chocolateBars = 0;
  let wrappers = 0
for (let i = n; i >= 0; i-= c) {
  if (i != n) {
  chocolateBars+=1
  }
}
wrappers = chocolateBars;
for (let i = wrappers; i > 0; i -= m) {
if (wrappers >= m) {
  chocolateBars+=1
  wrappers-= m;
  wrappers+=1
}
 }
 return (chocolateBars)
}
```
My brother just brought dinner over so I'll work on passing the other test cases after dinner.
___
21:09 -- I'm back. Let's try to refactor our code so that we can pass all of the test cases.

21:14 -- The test cases aren't very useful because there are so many situations (~100), it would be basically impossible to go through all of them one by one to see what went wrong.

From the 4-5 scenarios I've tried out of the failing test cases, my code output exactly what it needed to. That's why I'm feeling confused about what is wrong.

21:30 -- It was a lot of work, but I finally found a solution that passes every test case. Here it is:
```
function chocolateFeast(n, c, m) {
  let chocolateBars = 0;
  let wrappers = Math.floor(n/c);
for (let i = n; i >= 0; i-= c) {
  if (i != n) {
  chocolateBars+=1
  }
}

for (let i = wrappers; wrappers >= m; i -= m) {
if (wrappers >= m) {
  chocolateBars+=1
  wrappers-= m;
  wrappers+=1
}
 }
 return (chocolateBars)
}
```
21:31 -- Let's go over everything. First, we have a function *chocolateFeast* that has three parameters: *n*: an integer representing the amount of money Bobby is starting with, *c*: an integer representing the cost of a chocolate bar, and *m*: an integer representing the number of wrappers Bobby can turn in for a free chocolate bar.

Our job is to figure out how many chocolate bars Bobby can get.

Note that we're making a few assumptions. The first assumption is that Bobby will use all of his money. The second assumption is that Bobby will immediately turn in his wrappers for a free bar of chocolate if he has enough wrappers.

With that being the case, let's look at our problem's basic setup:
```
function chocolateFeast(n, c, m) {

}
```
21:34 -- I've also defined a few additional variables: *chocolateBars* and *wrappers*, both of which are initialized to the result of Math.floor(n/c).

In other words, we're initializing those two variables to the value of our money divided by the cost of a chocolate bar, and we're taking that result and rounding it down to the nearest integer.
```
function chocolateFeast(n, c, m) {
  let chocolateBars = Math.floor(n/c);
  let wrappers = Math.floor(n/c);
```
21:41 -- Next, we're going to use a for loop. Our for loop has a variable *i* which is initialized to the value of *wrappers*.

Our for loop will continue running for as long as *wrappers* is greater than or equal to *m* (the number of wrappers Bobby need to exchange for a free chocolate.) Finally, we're decrementing *i* by *m*.

Now that we've finished talking about the three expressions governing this for loop, let's talk about the contents within the loop. Everytime our loop runs, we increment *chocolateBars* by one, and decrement *wrappers* by *m*.

This is because our wrappers should decrease everytime we successfully exchange them for a chocolate bar, and our number of chocolate bars should increase by one everytime we make a successful exchange.

After we finish decrementing *wrappers*, we'll then increment *wrappers* by one because after getting a free chocolate bar we can eat the chocolate bar and have an additional wrapper to trade in.

Finally, after we eventually break out of this loop, we'll return *chocolateBars* as our solution to this algorithm!
```
function chocolateFeast(n, c, m) {
    let chocolateBars = Math.floor(n / c);
    let wrappers = Math.floor(n / c);

    for (let i = wrappers; wrappers >= m; i -= m) {
        chocolateBars += 1
        wrappers -= m;
        wrappers += 1
    }
    return (chocolateBars)
}
```
We did it!

21:54 -- If you were paying attention, you probably noticed that while explaining my solution to the 'Chocolate Feast' algorithm that I found many ways to refactor my code.

That's why I love teaching others and explaining coding concepts to others -- doing so also help you yourself internalize the various concepts.

21:56 -- Anyway, I now have 466 points which is good enough for a rank of 178,222 on HackerRank's global leaderboard for algorithms and data structures.

22:03 -- I was reading and seeing what I was going to be working with during my next coding session. When I come back, I'll work on the [Beautiful Triplets](https://www.hackerrank.com/challenges/beautiful-triplets/problem) algorithm.
___
23:01 -- Let's go for one more coding session.

23:03 -- Oh god this problem is giving me a headache already. Oh well :p. I'll work to solve it, and then explain things afterwards.

23:08 -- Here's our problem's basic setup:
```
function beautifulTriplets(d, arr) {

}
```
23:09 -- The nice thing about this problem is that they already sorted our array in ascending order.

23:12 -- Added our first for loop:
```
function beautifulTriplets(d, arr) {
for (let i = arr.length - 1; i >= 0; i--) {
  console.log(arr[i])
 }
}
```
23:20 -- Still plugging along:
```
function beautifulTriplets(d, arr) {
for (let i = arr.length - 1; i >= 2; i--) {
  console.log( `outer is: ${arr[i]}` )
  for (let ii = i -1; ii >= 0;ii--) {
    if (arr[i] - arr[ii] === d) {
      console.log("half beautiful!")
    }
    console.log(`inner is: ${arr[ii]}`)
  }
 }
}
```
23:28 -- I've solved this algorithm! Here's my solution:
```
function beautifulTriplets(d, arr) {
let beautifulTriplets = 0

for (let i = arr.length - 1; i >= 2; i--) {
  for (let ii = i -1; ii >= 0;ii--) {
    if (arr[i] - arr[ii] === d) {
      for (let j = arr[ii]; j >= 0; j--) {
        if (arr[ii] - arr[j] === d) {
          beautifulTriplets+=1
        }
      }
    }
  }
 }
 return beautifulTriplets
}
```
23:31 -- Let's talk about our solution.

23:32 -- We have a function *beautifulTriplets* that has two parameters *d* and *arr*. *d* is an integer that represents what we would define as a beautiful number. *arr* is an array of integers sorted in ascending order.

Our job is to look at *arr* and find all of the possible combinations of beautiful triplet numbers ([Click here](https://www.hackerrank.com/challenges/beautiful-triplets/problem), to go to this algorithm's page and read a more articulate and detailed problem definition).

Anyway, I've also defined an additional variable *beautifulTriplets* which is initialized to 0 and will be used to count the possible combinations of beautiful triplets.

Here's what our basic problem setup looks like:
```
function beautifulTriplets(d, arr) {
let beautifulTriplets = 0
```
23:37 -- Next, we have a for loop that we'll use to iterate through almost of the items in our array in reverse order.

The reason we don't want to loop over the first two items in our array *arr[0]* and *arr[1]*, is because we need at least three numbers to have a group of beautiful triplets.

Thus, iterating over these array items in our outer array would be redundant and a waste of resources.
```
function beautifulTriplets(d, arr) {
let beautifulTriplets = 0

for (let i = arr.length - 1; i >= 2; i--) {
 }
}
```
23:42 -- Next we have a second for loop. This for loop will also loop backwards through our array from largest numbers to smallest numbers. If at any point we find a number that is smaller than arr[i] and when said smaller number is subtracted from arr[i] also equals *d* or in other words:
> if (arr[i] - arr[ii] === d)

It means we're on the brink of possibly having a group of beautiful triplets, and that we also need a 3rd layer for loop (nested within our already nested 2nd layer for loop).

This 3rd layer for loop will also iterate through our array in reverse to see if we can find a number that is smaller than arr[ii] but when said smaller number is used to subtract from arr[ii] and gives us the result of *d*, or in other words:
> if (arr[ii] - arr[j] === d)

we'll know we have a group of beautiful triplets and thus can increment *beautifulTriplets* by one.

```
function beautifulTriplets(d, arr) {
let beautifulTriplets = 0

for (let i = arr.length - 1; i >= 2; i--) {
  for (let ii = i -1; ii >= 0;ii--) {
    if (arr[i] - arr[ii] === d) {
      for (let j = arr[ii]; j >= 0; j--) {
        if (arr[ii] - arr[j] === d) {
          beautifulTriplets+=1
        }
      }
    }
  }
 }
}
```
23:48 -- Eventually, after all of our loops terminate and we break out of them, we'll then return *beautifulTriplets* as our solution to this algorithm!
```
function beautifulTriplets(d, arr) {
let beautifulTriplets = 0

for (let i = arr.length - 1; i >= 2; i--) {
  for (let ii = i -1; ii >= 0;ii--) {
    if (arr[i] - arr[ii] === d) {
      for (let j = arr[ii]; j >= 0; j--) {
        if (arr[ii] - arr[j] === d) {
          beautifulTriplets+=1
        }
      }
    }
  }
 }
 return beautifulTriplets
}
```
Wow, this problem was a bit of a handful. Read over the original problem explanation a few times, try to understand my solution, and try to come up with your own solution.

If you stick with it, eventually you'll understand this algorithm and be able to produce a solution! :D

23:54 -- Well, we've gotten over 6 hours of coding in, just barely ;)

I now have 486 points on HackerRank which is good enough for a rank of 170,107 globally on the algorithms and data structures leaderboard.

23:57 -- Tomorrow I'll solve the CamelCase algorithm during my first coding session. But, tomorrow I also have some other professional obligations so it's very likely I will not reach 6 hours of coding tomorrow.

But, at the very least... I will at least commit to doing 6 hours of highly productive work tomorrow :D
___
**Total time spent coding today**: 6 hours 16 minutes

**Total time spent coding thus far in June 2019**: 51 hours 9 minutes

**Total lifetime hours of coding**: 622 hours 52 minutes