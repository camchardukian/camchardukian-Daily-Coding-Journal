# Saturday June 15th, 2019 Daily Coding Journal

16:27 -- I've had a lot of issues with productivity this week. In fact, thus far this week I've only spent 4 hours and 45 minutes programming.

That's simply unacceptable. I know I've traveled around the world and have jetlag, but I need to get it together. Let's go!

16:28 -- On HackerRank I currently have 91 points which is good for a global rank of 673,953.

16:29 -- The first thing I'll work on today is the [time conversion algorithm on HackerRank](https://www.hackerrank.com/challenges/time-conversion/problem).

16:30 -- Let's go!

16:31 -- Defining this problem is fairly easy. We have a function *timeConversion* that takes in a parameter *s*. We will pass a string as an argument to *s*.

That string passed to *s* will be in the format:
> hh:mm:ssAM or hh:mm:ssPM

Our job is to convert the string passed to our function from 12-hour clock format to 24-hour format.

16:36 -- Let's do our basic 1 minute setup and log something (anything!) to the console for sanity and momentum:
```
function timeConversion(s) {
console.log(s);
}
timeConversion("07:05:45PM")
```
16:39 -- The first thing I'm immediately thinking about is that if our passed string is "AM" we can just remove the "AM" to get our answer. Or so it seems...

16:43 -- I'm thinking about something along these lines:
```
function timeConversion(s) {
for (let i = 0; i < s.length - 2; i++) {
  console.log(s[i])
}
}
timeConversion("07:05:45AM")
```
Obviously this logic isn't complete -- we still need to add an *if else statement*, but doing so shouldn't be too difficult using the indexOf() method.

16:49 -- Moving along:
```
function timeConversion(s) {
if (s.indexOf("AM")) {
for (let i = 0; i < s.length - 2; i++) {
  console.log("contains AM")
}
}
else {
  console.log("does not contain AM")
}
}
timeConversion("07:05:45AM")
```
16:55 -- Making more progress but I need to clean things up a bit:
```
function timeConversion(s) {
  let result = [];
if (s.indexOf("AM") != -1) {
for (let i = 0; i < s.length - 2; i++) {
  result.push(s[i])
}
console.log(result.join(""))
}
else {
  result.push("false")
}
console.log(result)
}

timeConversion("07:05:45PM")
```

17:20 -- My code passes half of the test cases. Need. to. keep. going.
```
function timeConversion(s) {
  let result = [];
  for (let i = 0; i < s.length - 2; i++) {
  result.push(s[i])
}
if (s.indexOf("AM") != -1) {
result = result.join("")
}
else {
result[1] = parseInt(result[1])+ 12;
result.shift();
result = result.join("");
}
return result
}
timeConversion("07:05:45PM")
```
17:34 -- Wow, that problem was a bit more complicated than I initially thought. With that being said, here's my working solution:
```
function timeConversion(s) {
  let result = [];
  for (let i = 0; i < s.length - 2; i++) {
  result.push(s[i])
}
if (s.indexOf("AM") != -1) {
  if (result[0] > 0 && result[1] == 2) {
result[0] = 0
result[1] = 0
result = result.join("");
  }
  else {
result = result.join("");
}
}
else {
  if (result[0] > 0 && result[1] < 2) {
 result[0] = parseInt(result[0])+ 1;
 result[1] = parseInt(result[1]) + 2;
 result = result.join("");
  }

  else if (result[0] > 0 && result[1] == 2) {
  result = result.join("");
}

  else {
      result[1] = parseInt(result[1])+ 12;
      result.shift();
      result = result.join("");
  }
}
return result
}
```
17:36 -- I'm going to take a quick bathroom break, and get some water. Then I'll explain everything.
___

17:45 -- Alright, I'm back. Let's break things down.

17:46 -- First we create a function *timeConversions* which has a parameter *s* that takes in a string for an argument. We also initialize our result variable to an empty array.
```
function timeConversion(s) {
  let result = [];
}
```
17:48 -- Next, we use a for loop to loop through the string passed to *s*, pushing everything except for "AM" or "PM" to our results array.
```
  for (let i = 0; i < s.length - 2; i++) {
  result.push(s[i])
}
```
17:50 -- Moving on, the next thing we need to identify is whether our string passed to *s* contains "AM". We can do this using the indexOf() method.
```
s.indexOf("AM")
```
17:52 -- If our string contains "AM" we can simply join our results array (converting it to a string in the process), return that, and we're finished... Unless we have a situation like 12:15A.M. or 12:30A.M.

12:15am in the 24-hour system should display as 00:15. For that reason, we add an additional *if statement* saying that if our array starts with "12" (i.e. the first item is 1 and the second item is 2), we convert the first two items in our array to 0 in order to correctly display our time as starting at the 0th hour.
```
function timeConversion(s) {
  let result = [];
  for (let i = 0; i < s.length - 2; i++) {
  result.push(s[i])
}
if (s.indexOf("AM") != -1) {
  if (result[0] > 0 && result[1] == 2) {
result[0] = 0
result[1] = 0
result = result.join("");
  }
  else {
result = result.join("");
}
}
```
18:01 -- If our string doesn't contain "AM", however, we'd then proceed to our else clause in which we'd add 12 (by adding 1 to our array's first item and adding 2 to our arrays second item) to properly format our "PM" times to the 24-hour system.
>07P.M. --> 19

>10P.M. --> 22

>01P.M. --> 13

18:04 -- The one exception of course would be if we had 12pm. If we have 12pm, we don't want to add 12 because the time is already formatted properly and the 24th hour doesn't exist:
> 12:30P.M. --> 24:30
This obviously isn't what we're looking for. In the case of a P.M. formatted string, we can just return it as is (without including the P.M. of course!)

18:07 -- We've now gone through every scenario and can return our string!
```
function timeConversion(s) {
  let result = [];
  for (let i = 0; i < s.length - 2; i++) {
  result.push(s[i])
}
if (s.indexOf("AM") != -1) {
  if (result[0] > 0 && result[1] == 2) {
result[0] = 0
result[1] = 0
result = result.join("");
  }
  else {
result = result.join("");
}
}


else {
  if (result[0] > 0 && result[1] < 2) {
 result[0] = parseInt(result[0])+ 1;
 result[1] = parseInt(result[1]) + 2;
 result = result.join("");
  }

  else if (result[0] > 0 && result[1] == 2) {
  result = result.join("");
}

  else {
      result[1] = parseInt(result[1])+ 12;
      result.shift();
      result = result.join("");
  }

}
return result
}
timeConversion("12:05:45AM")
```
18:08 -- I hope that walking through this algorithm together helped you understand it!

18:14 -- I'm going to commit this journal entry to GitHub and then take a break to make a green smoothie. Hopefully I can continue to detox and get rid of these nagging stomach aches.
___
**Total time spent coding today**: 

**Total time spent coding thus far in June 2019**: 

**Total lifetime hours of coding**: 