# Tuesday June 25h, 2019 Daily Coding Journal

11:16 -- I just spent the last 5 minutes or so updating my journal entry from yesterday and committing it to GitHub. I wasted a lot of time yesterday.

As a result, not only am I starting today's journal entry late, but I'm also running on probably only 5 hours of sleep.

Today, I'd like to get 4 hours of quality coding in, and also get to sleep by 1am... which is quite a bit earlier than last night as bad as that sounds.

In any case, let's get working on the "Lisa's Workbook" algorithm.

11:20 -- For this algorithm, it looks like we have a girl named Lisa who has a workbook. The workbook has *n* number of chapters and the "i[th]" chapter of the book has arr[i] number of problems.

Each page can hold *k* number of problems, and only the chapter's last page will hold less than *k* number of problems.

We also know that each chapter starts on a new page, and thus a page will never contain problems coming from two different chapters.

In summary, given Lisa's book starts at page 1, we need to count the number of "special problems" in which a problem's index within a chapter is the same as the page number the problem is held on.

For example chapter 1 problem 1 is held on page 1 and thus it is special. Chapter 5 problem 5 is held on page 5 and thus it is special.

11:28 -- Now that we've defined the problem, I'm going to spend the next several minutes trying to solve it. I'll document my progress along the way and I'll then explain everything after reaching a final solution.

11:29 -- Initial problem setup:
```
function workbook(n, k, arr) {

}
```
11:33 -- I've written a for loop that runs 1 time for every chapter within our book:
```
function workbook(n, k, arr) {
for (let i = 1; i <= n; i++) {
  console.log(`We are on chapter ${i}`)
 }
}
```
11:38 -- I now have two loops which cycle through all of the chapters, and all of the problems in each chapter. One issue, however, is that I haven't yet accounted for page numbers -- at all.
```
function workbook(n, k, arr) {
for (let i = 1; i <= n; i++) {
  console.log(`We are on chapter ${i}`)
  
  for (let ii = 0; ii < arr[i-1]; ii++) {
    console.log(`hello ${ii}`)
  }
 }
}
```
11:43 -- Some more progress...
```
function workbook(n, k, arr) {
  let pageNumber = 0;
  let problemCount = 0;
for (let i = 1; i <= n; i++) {
  problemCount = 0;
  pageNumber+=1
  console.log(`We are on chapter ${i} and page ${pageNumber}`)
  
  for (let ii = 0; ii < arr[i-1]; ii++) {
    problemCount+=1
    console.log(`thus far there are ${problemCount} problems in this chapter`)
  }
 }
}
```
11:50 -- Here's where I'm at now:
```
function workbook(n, k, arr) {
  let pageNumber = 0;
  let problemCount = 0;
for (let i = 1; i <= n; i++) {
  problemCount = 0;
  pageNumber+=1
  console.log(`We are on chapter ${i} and page ${pageNumber}`)
  
  for (let ii = 0; ii < arr[i-1]; ii++) {
    problemCount+=1
   
    if (problemCount > k) {
      problemCount = 1
      pageNumber+=1
 
    }

  }
 }
console.log(pageNumber)
}
```
11:51 -- I'm going to take a quick break and then finish things when I come back around 12:15.
___
12:18 -- I'm back. Let's finish solving this algorithm.

12:22 -- Algorithm solution under construction hahaha:
```
function workbook(n, k, arr) {
  let pageNumber = 0;
  let problemsOnCurrentPage = 0;
  let problemNumberThisChapter = 1
  let specialProblems = 0;
for (let i = 1; i <= n; i++) {
  problemsOnCurrentPage = 0;
  pageNumber+=1
  console.log(`We are on chapter ${i} and page ${pageNumber}`)
  
  for (let ii = 0; ii < arr[i-1]; ii++) {
    problemsOnCurrentPage+=1
   
    if (problemsOnCurrentPage > k) {
      problemsOnCurrentPage = 1
      pageNumber+=1
    }
  }
 }
console.log(pageNumber)
}
```
12:27 -- I've produced a working solution to this algorithm that passed all of HackerRank's tests! Here's my solution:
```
function workbook(n, k, arr) {
  let pageNumber = 0;
  let problemsOnCurrentPage = 0;
  let problemNumberThisChapter = 0
  let specialProblems = 0;
for (let i = 1; i <= n; i++) {
  problemsOnCurrentPage = 0;
  pageNumber+=1
  problemNumberThisChapter = 0
  
  for (let ii = 0; ii < arr[i-1]; ii++) {
    problemsOnCurrentPage+=1
   problemNumberThisChapter+=1
    if (problemsOnCurrentPage > k) {
      problemsOnCurrentPage = 1
      pageNumber+=1
    }
    if (problemNumberThisChapter === pageNumber) {
      specialProblems+=1
    }
  }
 }
return (specialProblems)
}
```
12:28 -- Let's go over how this solution works. We have a function *workbook* that takes in 3 parameters: *n*: an integer representing the number of chapters in Lisa's workbook, *k*: an integer representing the maximum number of problems each individual page in the workbook can hold, and *arr*: an array of integers representing the number of problems for each chapter in the workbook.

Here's our basic setup for this algorithm:
```
function workbook(n, k, arr) {

}
```
12:32 -- Next, we're going to need several variables. These variables include:
* *pageNumber* -- The current page of the book we're on.
* *problemsOnCurrentPage* -- The number of problems we have on our current page.
* *problemNumberThisChapter* -- The number of problems in the current chapter we've already gone through.
* *specialProblems* -- The number of special problems we've had thus far. We'll eventually return this variable as our solution to the algorithm.

Apart from simply declaring the above variables, we're also going to initialize all of them to 0.
```
function workbook(n, k, arr) {
  let pageNumber = 0;
  let problemsOnCurrentPage = 0;
  let problemNumberThisChapter = 0
  let specialProblems = 0;
}
```
12:38 -- Now, we're going to add our first for loop. This for loop will run a number of times that's equivalent to the integer passed to *n* (the number of chapters in Lisa's book).

The role of this for loop is to move us along through all of the chapters in Lisa's book while also updating some values each time we start a new chapter.

Whenever we start a new chapter, that chapter is going to begin on a new page. Thus, with each iteration of our for loop, we're going to increment *pageNumber* by one.

We'll also update the values of *problemsOnCurrentPage* and *problemNumberThisChapter* to 0 each time we start a new chapter.
```
function workbook(n, k, arr) {
  let pageNumber = 0;
  let problemsOnCurrentPage = 0;
  let problemNumberThisChapter = 0
  let specialProblems = 0;
for (let i = 1; i <= n; i++) {
  problemsOnCurrentPage = 0;
  pageNumber+=1;
  problemNumberThisChapter = 0;
 }
}
```
12:44 -- Stay with me. We're on the home stretch. At this point, we need to do something while we're going through the problems in each chapter, before moving on to the next chapter.

Otherwise, we'd just be flipping from chapter to chapter with no regards for the actual contents of each chapter.

In other words, we're going to need a nested for loop. This nested for loop will run for as long as our variable *ii* is less than *arr[i-1]* -- the current position in *arr* (the number of problems in the chapter we're currently on).

With each iteration of our loop, we're going to increment *problemsOnCurrentPage* and *problemNumberThisChapter* by one.

Then, we'll evaluate if *problemsOnCurrentPage* is greater than *k*. If so, we'll increment *pageNumber* by 1, and update the value of *problemsOnCurrentPage* to equal 1, because we're going to a new page, and that new page currently houses 1 problem (the most recent problem we added).
```
function workbook(n, k, arr) {
  let pageNumber = 0;
  let problemsOnCurrentPage = 0;
  let problemNumberThisChapter = 0
  let specialProblems = 0;
for (let i = 1; i <= n; i++) {
  problemsOnCurrentPage = 0;
  pageNumber+=1;
  problemNumberThisChapter = 0;
  
  for (let ii = 0; ii < arr[i-1]; ii++) {
    problemsOnCurrentPage+=1
   problemNumberThisChapter+=1
    if (problemsOnCurrentPage > k) {
      problemsOnCurrentPage = 1
      pageNumber+=1
    }
  }
 }
}
```
12:52 -- If at any point the value of *problemNumberThisChapter* is equal to *pageNumber*, we'll know that we have a special problem and thus we increment our variable *specialProblems* by one.

Eventually, after we break out of our function's two loops, we'll return *specialProblems* as our solution to this algorithm!
```
function workbook(n, k, arr) {
  let pageNumber = 0;
  let problemsOnCurrentPage = 0;
  let problemNumberThisChapter = 0
  let specialProblems = 0;
for (let i = 1; i <= n; i++) {
  problemsOnCurrentPage = 0;
  pageNumber+=1;
  problemNumberThisChapter = 0;
  
  for (let ii = 0; ii < arr[i-1]; ii++) {
    problemsOnCurrentPage+=1
   problemNumberThisChapter+=1
    if (problemsOnCurrentPage > k) {
      problemsOnCurrentPage = 1
      pageNumber+=1
    }
    if (problemNumberThisChapter === pageNumber) {
      specialProblems+=1
    }
  }
 }
return (specialProblems)
}
```
12:54 -- Hopefully you were able to get some value out of this tutorial. Together you and I, let's keep practicing and improving our web development skills each day! :D

13:00 -- I now have 596 points which is good enough for a rank of 135,871 on HackerRank's global algorithm leaderboard.

13:01 -- During the next coding session, I'll work on solving the [Fair Rations](https://www.hackerrank.com/challenges/fair-rations/problem) algorithm.
___
17:47 -- I got some exercise. That's good. I also caught up on sleep that I allowed myself to fall behind on yesterday. Also good. I've been doing a good job since 11:15 today. 

Let's keep the momentum going. 1 hour at a time.

17:49 -- For the 'Fair Rations' algorithm, it looks like we're the ruler of some kingdom and we need to distribute bread.

Some of our subjects already have some loaves of bread, and because food is scarce, we need to distribute as few loaves as possible.

However, anytime we give someone a loaf of bread, subject *i* for example, we must also give a loaf of bread to the person immediately in front of or behind them (i+1 or i-1).

Our goal is make sure each subject has an even number of loaves of bread (Note: When we say even number of loaves we don't mean equivalent number of loaves, we're referring to even numbers, AKA not odd numbers).

If we can achieve the above, our function should return the minimum number of loaves necessary to meet the above conditions. 

If we cannot ensure every citizen has an even number of loaves, our function should return the string "NO".

17:58 -- Now that we've defined the problem, I'm going to start working on a solution. I'll update you as I progress, and then after I solve this algorithm we'll go over everything in more detail.

18:01 -- Here's our basic setup:
```
function fairRations(B) {

}
```
18:09 -- Here's some pseudocode I wrote to try to start thinking about the answer to this problem:
```
// Starting from the front of the array, skip over any numbers that are even.

// When we encounter an array item that has an odd value, increment that array item by 1, and increment loavesDistributed by 1.

// Then, increment the following item by 1, and increment loavesDistributed by 1 again. Repeat the process, until all items are even. Then return the number of loaves we had to give out.

// If we get to the end of the array and all items are not even, return "NO".
```
18:18 -- Almost finished...
```
function fairRations(B) {
  let loavesDistributed = 0;
for (let i = 0; i < B.length - 1; i++) {
  if (B[i] % 2 === 1) {
    B[i]+=1;
    B[i+1]+=1;
  loavesDistributed+=2
  }
 }
}
```
18:22 -- My solution passed all of HackerRank's tests! Here's my final solution:
```
function fairRations(B) {
  let loavesDistributed = 0;
for (let i = 0; i < B.length - 1; i++) {
  if (B[i] % 2 === 1) {
    B[i]+=1;
    B[i+1]+=1;
  loavesDistributed+=2
  }
 }
if ((B[B.length-1]) % 2 === 0) {
 return (loavesDistributed)
 }
else {
  return "NO"
 }
}
```
18:23 -- I'm going to go get a little more exercise (juggling a soccer ball outside), then I'll explain the above solution to you!
___
19:26 -- Just got some exercise in, ate an apple, and spent 15 minutes or so chatting with my parents. Now, let's explain the last algorithm.

19:28 -- Our goal is make sure each subject has an even number of loaves of bread (Note: When we say even number of loaves we don't mean equivalent number of loaves, we're simply referring to even numbers, AKA not odd numbers.)

For a full explanation of this problem, [click here](https://www.hackerrank.com/challenges/fair-rations/problem).

We have a function *fairRations* that has a parameter *B* which takes in an array of integers representing the number of loaves of bread each of our subjects currently has.

I've also declared a variable *loavesDistributed* which is initialized to 0 and is used for the purpose of counting how many total loaves of bread we've given to our kingdom's citizens.

```
function fairRations(B) {
  let loavesDistributed = 0;
}
```
19:31 -- Next, we have a for loop that iterates over all but the last item in our array. With each iteration of our loop, we see whether the current subject (B[i]) has an off number of loaves of bread. 

If so, we give a loaf of bread to the current subject (B[i]+=1). We also give a loaf of bread to the next citizen in line (B[i]+=1). Then, we note that we've just given two loaves of bread (loavesDistributed+=2).
```
function fairRations(B) {
  let loavesDistributed = 0;
for (let i = 0; i < B.length - 1; i++) {
  if (B[i] % 2 === 1) {
    B[i]+=1;
    B[i+1]+=1;
  loavesDistributed+=2
  }
 }
}
```
19:38 -- If we reach the last subject (B[B.length -1]), and they have an even number of loaves of bread ((B[B.length-1]) % 2 === 0), we return *loavesDistributed* as our solution to this algorithm because all of our citizens have an even number of loaves of bread!

Otherwise, we'll return the string "NO" as our solution because we were unable to meet the constraints set by the algorithm (we can't give the last person a loaf of bread, because if we did we'd also have to give then 2nd to last person a loaf of bread and then we'd still have one citizen with an odd number of loaves of bread).
```
function fairRations(B) {
  let loavesDistributed = 0;
for (let i = 0; i < B.length - 1; i++) {
  if (B[i] % 2 === 1) {
    B[i]+=1;
    B[i+1]+=1;
  loavesDistributed+=2
  }
 }
if ((B[B.length-1]) % 2 === 0) {
 return (loavesDistributed)
 }
else {
  return "NO"
 }
}
```
19:42 -- Way to follow through all the way to the end! If you feel you've gotten your head around this problem, try closing this file and solving the algorithm again for yourself!

19:50 -- I now have 621 points which is good enough for a rank of 129,717 on HackerRank's global leaderboard!

19:51 -- During my next coding session, I'll focus on solving the [Lonely Integer](https://www.hackerrank.com/challenges/lonely-integer/problem) algorithm.

___
**Total time spent coding today**: 

**Total time spent coding thus far in June 2019**: 

**Total lifetime hours of coding**: 