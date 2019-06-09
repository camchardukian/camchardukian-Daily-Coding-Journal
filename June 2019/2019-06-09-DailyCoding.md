# Sunday June 9th, 2019 Daily Coding Journal
17:22 -- Off to a bit of a late start today. Anyway, let's get started!

17:23 -- I now have 51 points on hackerrank for a world ranking of 872579. I'm going to further improve my position by solving another algorithm today!

17:26 -- I'm going to work on solving the [Grading Students algorithm](https://www.hackerrank.com/challenges/grading/problem).

17:27 -- First, let's define the problem. We have a teacher named Mr. Sam. In his class, the students all receive a score that ranges from 0-100. Anyone with a score less than 40 fails -- but... Mr. Sam also has a system for rounding grades in his class.

If the difference between the student's score and the next multiple of 5 is less than 3, Mr. Sam will round said student's grade up to the next multiple of 5.

The one exception is if the student's grade is less than 38. That is because even rounding a score from 24 or 33 to the next multiple of 3 wouldn't be enough to give the student a passing score.

17:37 -- I've done some basic groundwork. Here's the function I've set up thus far:
```
function gradingStudents(grades) {
for (let i = 0; i < grades.length; i++) {
  console.log(grades[i])
}
}
gradingStudents([94, 50, 31, 39, 63, 58])
```
My current code prints all of the grades one by one on their own line. Now I just have to implement the different rounding criteria.

17:45 -- I'm still going. I'm having a little bit of trouble figuring out whether I should divide by 5 or use the modulus operator or both. Here's my code update:
```
function gradingStudents(grades) {
for (let i = 0; i < grades.length; i++) {
  if (grades[i] <= 37) {
    console.log(grades[i])
  }
  else {
  console.log(grades[i] + " may or may not need rounding")
  }
}
}
gradingStudents([94, 50, 31, 39, 63, 58])
```

17:48 -- Let's try to think things through. We've already done some basic "filtering" (no pun intended) by stating that any number equal to or less than 37 doesn't need any processing and that we can simply return it back as is.

On the other hand, we still need to figure out how we should go about processing and rounding the remaining input...

I'm considering either creating a variable that has an index of numbers divisible by 5, for example our index could be:
>[40, 45, 50, 55, 60, 65, 70, 75, 80, 85, 90, 95, 100]

Barring that, I could also use a for loop. And the for loop could determine what the remainder is of our input when divided by 5. I think that if the remainder is 1 or 2, we could then add said remainder to our number as a way of "rounding" up.

18:02 -- I've now written enough code to identify which numbers need rounding, and which numbers are fine as is. Here's my current progress:
```
function gradingStudents(grades) {
for (let i = 0; i < grades.length; i++) {
  if (grades[i] <= 37) {
    console.log(grades[i])
  }
  else {
  if (grades[i] % 5 > 2) {
    console.log(grades[i] + "needs rounding")
  }
  else {
    console.log(grades[i] + "doesn't need rounding")
  }
  }
}
}
gradingStudents([94, 50, 31, 39, 61, 57])
```
The only thing I have left to do is actually round to the next multiple of 5.

18:03 -- I'm going to take a quick bathroom and stretching break. Then I'll solve the rest of this problem.
___
18:08 -- Alright I'm back.

18:17 -- I thought I'd solved the problem with the following code:
```
function gradingStudents(grades) {
for (let i = 0; i < grades.length; i++) {
  if (grades[i] <= 37) {
    console.log(grades[i])
  }
  else {
  if (grades[i] % 5 > 2) {
    console.log(grades[i] + (5 - grades[i] % 5))
  }
  else {
    console.log(grades[i])
  }
  }
}
}
gradingStudents([94, 50, 31, 39, 61, 57])
```
While, I was close, I didn't see the following bit in the instructions:
>It should return an integer array consisting of rounded grades.

Now I have to go back and refactor my code so that I push my rounded numbers to an array, (or use the map method).

18:24 -- I feel like this challenge somewhat poorly defined how it wanted us to return our results. I thought that for this challenge we needed to print a single number on each line to the console.

It turns out that all I really had to do, however, was return an array of the numbers we needed and the hackerrank website would handle the printing of each number to its own individual line under the hood.

In any case, here was my final solution:
```
function gradingStudents(grades) {
  let results = []
for (let i = 0; i < grades.length; i++) {
  if (grades[i] <= 37) {
    results.push(grades[i])
  }
  else {
  if (grades[i] % 5 > 2) {
    results.push(grades[i] + (5 - grades[i] % 5))
  }
  else {
    results.push(grades[i])
  }
  }
}
return results
}
```
1. We create a function *gradingStudents()*.
1. We initialize our results variable to an empty array.
1. We create a for loop to cycle through all the "student scores" passed to our gradingStudents array via the *grades argument*.
1. We push any grades under 37 directly to our array "as-is" because we know that those students' grades are guaranteed to be a failing score.
1. If the students grade is above 37, we see what the "grade's" number is when divided by 5. If when divided by 5 we identify that the remainder is greater than 2, we take **5 - the remainder** and add it to grades[i] before pushing it to our results array.
1. If the remainder was less than 2, however, we'd skip our *if clause* above and simply push *grades[i]* to our results array "as-is".
1. Finally, we return our results array.

Hope you found this useful! I'm going to commit everything to GitHub and then go get dinner!
___
**Total time spent coding today**: 

**Total time spent coding thus far in June 2019**: 

**Total lifetime hours of coding**: