# Monday July 1st, 2019 Daily Coding Journal
0:04 -- Man I'm stuck. I've worked on this algorithm for more than 2.5 hours already and I'm just not advancing any further. I'm calling it quits.
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
return result
}
if (leftovers) {
if ((s + leftovers) <= n) {
result = (s + leftovers) -1
return result
}
else if ((s + leftovers) > n) {
result = s - leftovers + 1
return result
}
}
else {
if (leftovers === false) {
if ((s + m) <= n) {
result = (s + m) - 1
}
else {
result = s - n + m
}
return result
}
}
}
```
0:05 -- Anyway, I now have 780.7 points on HackerRank, which is good enough for a rank of 100,219 on HackerRank's global algorithm leaderboard.

0:08 -- Tomorrow I'll try to solve the [Super Reduced String](https://www.hackerrank.com/challenges/reduced-string/problem) algorithm.

0:15 -- I've committed everything from yesterday to GitHub. I'm going to commit this entry to GitHub now, and then work on some mostly non-code related stuff for the rest of the night.

___
**Total time spent coding today**: 

**Total time spent coding in June 2019**: 

**Total lifetime hours of coding**: 