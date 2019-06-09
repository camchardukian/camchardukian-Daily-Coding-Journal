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
22:23 -- Let's get another quick programming session in! Let's try to race and solve an algorithm before 23:00!

22:24 -- I currently have 61 points and my global ranking on hackerrank is 813,659.

22:26 -- I'm about the start working on hackerrank's [birthday cake candle](https://www.hackerrank.com/challenges/birthday-cake-candles/problem) algorithm. Let's see how far we can get in the next 30 minutes!

22:27 -- The first thing we need to do is define the problem. We have our niece's birthday party and we want to give her one candle for each year she has lived.

However, some of the candles will be of different heights. Our niece can only blow out the tallest candles. Our job is to find the tallest candle(s) and see how many of them there are.

To do this, we need to look at the array of numbers that is passed to our function. If the array of numbers is the following:
> [5, 2, 3, 2, 5]

We should log **2** to the console because our largest number in the array is 5, and that number is repeated two times.

22:33 -- Now I'll take a few minutes to start actually implementing the code...

22:36 -- Here's my basic setup thus far...
```
function birthdayCakeCandles(ar) {
  let counter = 0;
for (let i = 0; i < ar.length; i++) {
  console.log(ar[i])
}
}
birthdayCakeCandles([1, 5, 2, 3, 3, 3, 4, 2, 5, ])
```
22:43 -- I've added functionality for determining whether the next number in the array is greater than/equal to, or less than the current number in the array.
```
function birthdayCakeCandles(ar) {
  let counter = 0;
for (let i = 0; i < ar.length; i++) {
  if (ar[i] < ar[i+1] ) {
  console.log(ar[i] + "is less than" + ar[i + 1])
}
else if (ar[i] >= ar[i + 1]) {
  console.log(ar[i] + "is more than or equal to" + ar[i+1])
}
else {
  console.log("you at da end of da array bro")
}
}
}
birthdayCakeCandles([1, 5, 2, 3, 3, 3, 4, 2, 5,])
```
The next logical step is increasing or resetting my counter based on this information.

22:50 -- Code has gotten pretty ugly:
```
function birthdayCakeCandles(ar) {
  let counter = 0;
  let currentNumber = 0;
for (let i = 0; i < ar.length; i++) {
  if (currentNumber < ar[i+1] ) {
  counter = 0
  currentNumber = ar[i+1]
  console.log(currentNumber)
}
else if (currentNumber >= ar[i + 1]) {
  counter+=1
}
else {
  if (counter === 0) {
    counter += 1
  }
}
}
return counter
}
birthdayCakeCandles([1, 5, 2, 3, 3, 3, 4, 2, 5])
```
I need to rethink about what I'm doing...

23:00 -- I did it!! Finished at 23:00 *EXACTLY*

Here was my code that I couldn't figure out why it wasn't working:
```
function birthdayCakeCandles(ar) {
  let counter = 0;
  let currentNumber = 0;
for (let i = 0; i < ar.length; i++){
  console.log("current number is: " + currentNumber)
  if (currentNumber < ar[i+1] ) {
  counter = 1
  currentNumber = ar[i+1]
  console.log("if clause" + currentNumber)
}
else if (currentNumber = ar[i + 1]) {
  counter+=1
  console.log("ELSE IF clause" + currentNumber)
}
else {
  console.log(currentNumber + " is greater than " + ar[i+1])
}
}
return counter
}
birthdayCakeCandles([1, 5, 2, 3, 3, 3, 4, 2, 5])
```
For a loooong time, I couldn't figure out why it wasn't working. It turns out, the problem was that in my else if clause I was accidentally assigning currentNumber that value of ar[i+1] using a single equals sign rather than comparing them using double or triple equals. 

Here is my complete solution that passed hackerrank's tests...

Actually, it doesn't.

23:11 -- I had to do a little bit of debugging, but anyway, here's my final solution that passed all of hackerrank's algorithms:
```
function birthdayCakeCandles(ar) {
  let counter = 0;
  let biggestNumber = 0;
for (let i = 0; i < ar.length; i++){
  if (biggestNumber < ar[i] ) {
  counter = 1
  biggestNumber = ar[i]
}
else if (biggestNumber === ar[i]) {
  counter+=1
}
}
return counter // this is where we return the answer hackerrank is looking for.
}
birthdayCakeCandles([3, 2, 1, 3, 3, 3, 2,])
```
Let me explain what's going on here...
1. We have a function *birthdayCakeCandles* that has a parameter *ar*.
1. We initialize our *counter* and *biggestNumber* variables to 0.
1. We create a for loop that has a variable *i* initalized to 0, increments by 1 each time the loop is run, and continues running until *i* is no longer less than the length of our array.
1. If the value of *biggestNumber* is less than *ar[i]*, we set our *counter* variable to 1 and set our *currentValue* variable to the value of *ar[i]*. *Why?* Because if *ar[i]* is greater than *biggestNumber* it's obvious that what we thought was the biggestNumber (or tallest candle) was not in fact the biggest candle. It's also of course important for us to reset out counter variable to 1 if we find a new biggest candle.
1. If our *biggestNumber* variable is equal to *ar[i]* we can increment counter by one because we know that our biggest candle has at least one (or more if we repeat this scenario multiple times) fellow candle(s) of an equivalent height.
1. Finally, we return the value of counter, which is the expected output for hackerrank!

11:23 -- Wow, that was some mental stimulation alright ;) I have to say I genuinely enjoy doing these algorithms.

They are a fun way to challenge the brain, and they also help you become more comfortable with JavaScript. A much better use of time than Sudoku no doubt!

11:24 -- Anyway, I'm going to get everything committed to GitHub. Record a video for the daily developer channel, and then get some sleep.
___
**Total time spent coding today**: 2 hours 31 minutes

**Total time spent coding thus far in June 2019**: 20 hours 50 minutes

**Total lifetime hours of coding**: 592 hours 8 minutes