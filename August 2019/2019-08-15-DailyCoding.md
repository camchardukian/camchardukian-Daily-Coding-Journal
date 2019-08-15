# Thursday August 15th, 2019 Daily Coding Journal

8:33 -- Yesterday I got my daily coding habit started up again. I didn't put in as much time as I would've liked, but at least I sat down and did something. 

I'm hoping to build upon yesterday, by going a little bit deeper into the programming processes today.

8:49 -- Here's some pseduocode I just put together:
```
// start calculating square roots from the bottom end of our range "a".

// if the square root of "a" is an integer, we'll know that is our first square integer and push it to our results array. We'll also update the value of current to equal the square root of a.

// If the square root of "a" is NOT an integer, we WON'T push the square root of A to our results array. We'll then update the value of "current" to equal Math.ceil the square root of "a".

// We'll then use a loop whose function will be to increment current by 1, and if "current" squared is less than "b", we'll push the value of "current" to our array "results", increment "current" by 1, and repeat the process for as long as "current" squared is less than "b".

// We can then take the length of our "results" array as our solution to this algorithm!
```

8:57 -- My pseudocode worked out exactly as planned! :D Here's my final solution:
```
function squares(a, b) {
  let result = [];
  let current;

  current = Math.sqrt(a);

  if (current > 0 && current == Math.floor(current)) {
    result.push(current)
    current+=1
  }
  else {
    current = Math.ceil(current);
  }

  for (let i = current; current*current <= b; current+=1) {
    result.push(current)
  }

  return (result.length)
}
```

During my next coding session I'll explain exactly why this solution works. For now, however, I'm just going to take a minute to appreciate the small victory of getting a coding session in early in the morning.

I haven't done that in a long time! It's great to always be hungry for more, but it's also important to appreciate the small successes along the way :)
___
**Total time spent coding today**: 

**Total time spent coding thus far in August 2019**: 

**Total lifetime hours of coding**: 