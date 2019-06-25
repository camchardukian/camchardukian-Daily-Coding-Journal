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
**Total time spent coding today**: 

**Total time spent coding thus far in June 2019**: 

**Total lifetime hours of coding**: 