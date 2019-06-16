# Sunday June 16th, 2019 Daily Coding Journal

6:41 -- I feel like I'm finally starting to get back into some kind of rhythm. Let's get off to an early start today and produce.

6:44 -- I currently have 106 points on HackerRank which is good for a global rank of 600,012.

6:46 -- I'm working on the [Breaking the Records algorithm on HackerRank](https://www.hackerrank.com/challenges/breaking-best-and-worst-records/problem).

6:47 -- Let's define the problem. There's a basketball player named Maria. She wants to count how many times in a season she breaks her record for most points and least points.

The points she scores in her first game establishes the baseline through which we'll make our comparisons to evaluate whether she broke a record or not.

We have a function *breakingRecords* that has a parameter *scores* that takes in an array of numbers as its argument.

Our goal is to use this function to return two numbers separated by a space that respectively represent the number of times she broke her record for highest points and lowest points in a game throughout her season.

6:56 -- It's a start:
```
function breakingRecords(scores) {

}
```

6:59 -- Moving forward...
```
function breakingRecords(scores) {
  let result = [0, 0];
for (let i = 0; i < scores.length; i++) {
}
}
```
7:11 -- Almost finished:
```
function breakingRecords(scores) {
  let maxMinRecord = [0, 0];
  let maximum = scores[0];
  let minimum = scores[0];
for (let i = 0; i < scores.length; i++) {
  if (scores[i] > maximum) {
    console.log(`${scores[i]} is greater than ${maximum}`)
        maximum = scores[i]
        maxMinRecord[0]+=1
  }
  else if (scores[i] < minimum) {
    console.log(`${scores[i]} is less than ${minimum}`)
    minimum = scores[i]
    maxMinRecord[1]+=1
  }
}
  console.log(maxMinRecord)
}
```
Just need to clean things up a little and console.log() my maxMinRecord array in the correct format.

7:17 -- Finished! Here's my final solution:
```
function breakingRecords(scores) {
  let maxMinRecord = [0, 0];
  let maximum = scores[0];
  let minimum = scores[0];
for (let i = 0; i < scores.length; i++) {
  if (scores[i] > maximum) {
        maximum = scores[i]
        maxMinRecord[0]+=1
  }
  else if (scores[i] < minimum) {
    minimum = scores[i]
    maxMinRecord[1]+=1
  }
}
return (maxMinRecord.join(" "))
}
breakingRecords([10, 5, 20, 20, 4, 5, 2, 25, 1])
```
7:18 -- I'm going to take a break to stretch and have breakfast. Then, I'll explain everything.
___
**Total time spent coding today**: 

**Total time spent coding thus far in June 2019**: 

**Total lifetime hours of coding**: 