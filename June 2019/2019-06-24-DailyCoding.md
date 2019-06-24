# Monday June 24th, 2019 Daily Coding Journal

12:29 -- I finally finished my developer resume yesterday. I'll have some family members look over it to help me identify areas that are too wordy, or difficult to understand.

Then... I think I'll be in business ;)

12:30 -- In any case, I'm going to quick move my clothes over from the washer to the dryer. Then, I'll try to solve the HackerRank in a String algorithm before making a trip to the dentist.

12:40 -- I'm back, I've only got about 30 minutes before I need to head out, but let's see if we can get anything done.

12:42 -- Because I'm a bit short on time, I'm not going to go in-depth about explaining this problem now. I'm just going to try to solve it, document my progress, and explain things later.

12:46 -- Basic function setup:
```
function hackerrankInString(s) {
console.log(s)

}
```
12:55 -- Final solution:
```
function hackerrankInString(s) {
let hackerrankArray = ['h', 'a', 'c', 'k', 'e', 'r', 'r', 'a', 'n', 'k'];
for (let i = 0; i < s.length + 1; i++) {
  if (hackerrankArray.length > 0) {
  if (s[i] === hackerrankArray[0]) {
    hackerrankArray.shift()
  }
  }
  else {
    return "YES"
  }
}
return "NO"
}
```
WOW! We ended up solving this algorithm **super** quickly. I need to arrange my commit this journal entry to GitHub, hang my clothes, eat an apple, brush my teeth, and change into nicer clothes before going out.

12:56 -- I'll explain my algorithm solution during my next coding session -- perhaps even in the car on the way to the dentist if my mom doesn't find my anti-socialness too rude hahaha.
___

___
**Total time spent coding today**: 

**Total time spent coding thus far in June 2019**: 

**Total lifetime hours of coding**: 