# Saturday June 22nd, 2019 Daily Coding Journal

0:02 -- Just finished commiting Friday's (June 21st, 2019) journal entry to GitHub.

0:03 -- Here's my final solution for the Kangaroo algorithm:
```
function kangaroo(x1, v1, x2, v2) {
    if (v1 > v2) {
        while (x1 < x2) {
            x1 += v1;
            x2 += v2;
            if (x1 === x2) {
                return "YES"
            }
        }
    }
    else if (v1 < v2) {
        while (x1 > x2) {
            x1 += v1;
            x2 += v2;
            if (x1 === x2) {
                return "YES"
            }
        }
    }
    return "NO"
}
```
0:04 -- I will explain this algorithm in the morning. Now, however, I'm going to record a video for the [Daily Developer show](https://www.youtube.com/channel/UCRUPCpCWCL6Mr-0QWNje29Q/), and push an initial commit of this entry to GitHub.
___
See you in the morning!

20:38 -- \*ugh\*. Today has been a pretty horid day thus far. I woke up last night after 1.5 hours of sleeping, and basically wasted the entire day after that.

I think now I'm probably running on about 5 hours of sleep and I'm feeling exhausted and pretty disgusted about how I squandered the time God, or the universe allocated for me to use today.

With that being said, I have been reminded about one lesson... The importance of exercise in the role in contributing to quality sleep. :D

The one positive thing I've done thus far today is get an hour of exercise in.

Now I'm going to try to get at least a little bit of coding in to maintain my momentum, and daily habit.

20:42 -- Let's explain the [Kangaroo algorithm](https://www.hackerrank.com/challenges/kangaroo/problem) from last night.

20:43 -- We have two kangaroos. Our job is to figure out if these two kangaroos will ever land in the same place after the same number of jumps.

If so, our function should return "YES". Otherwise, our function should return "NO".

To accomplish this task, we have a function *kangaroo* that has four parameters:
* *x1* -- The starting position for kangaroo 1.
* *v1* -- The jump distance for kangaroo 1.
* *x2* -- The starting position for kangaroo 2.
* *v2* -- The jump distance for kangaroo 2.

Here's our basic function setup:
```
function kangaroo(x1, v1, x2, v2) {
} 
```
20:49 -- Our logic for solving this problem is pretty simple. If our first kangaroo has a larger jump distance than our second kangaroo (*v1* > *v2*), we'll run a for loop for as long as the second kangaroo is farther along than the first kangaroo (x1 < x2).

Once this stops being the case, we would of course break out of our loop because if the fastest kangaroo ever gets ahead, any further looping becomes unnecessary because the slower kangaroo will never be able to catch up.

Moving forward, for each iteration of our loop, we'll advance our kangaroo's positions (*x1* and *x2*) by the value of the distance they can make with each jump (*v1* and *v2* respectively).

Each time through our loop, we'll also check to see if our kangaroos are in the same position (x1 === x2). If so, we'll return "YES" as our solution to this algorithm.

```
function kangaroo(x1, v1, x2, v2) {
if (v1 > v2) {
  while (x1 < x2) {
    x1+= v1;
    x2+= v2;
    if (x1 === x2) {
    return "YES"
    }
  }
 }
}
```
20:57 -- Of course, it's important to note that sometimes our first kangaroo will be faster and sometimes our second kangaroo will be faster. If the first kangaroo is faster we'll utilize our if statement above.

Otherwise, we can simply reverse the logic to create an if else statement to govern a scenario in which the second kangaroo is faster.

Finally, regardless of whether our passed arguments lead to us using the logic in our if statement or the logic in our if else statement, one thing is certain.

Our two kangaroos will either be in the same spot after the same numbers of jumps at some point (in this scenario we'd return "YES"), OR neither our if nor or if else statement returned anything, and thus we'd return "NO" as our solution to this algorithm.
```
function kangaroo(x1, v1, x2, v2) {
if (v1 > v2) {
  while (x1 < x2) {
    x1+= v1;
    x2+= v2;
    if (x1 === x2) {
    return "YES"
    }
  }
 }
  else if (v1 < v2) {
    while (x1 > x2) {
      x1+= v1;
      x2+= v2;
      if (x1 === x2) {
        return "YES"
      }
    }
  }
  return "NO"
}
```
21:03 -- Hopefully you were able to follow along. For more algorithm challenges, you can go to [HackerRank's algorithm challenges page](https://www.hackerrank.com/domains/algorithms), and for more solutions check out my [HackerRank algorithm solutions GitHub repo](https://github.com/camchardukian/hackerrank-algorithms).

21:08 -- Man I'm feeling exhausted now. I'm going to take a break. I'm not sure if I'll get more coding in tonight or if I'm just going to try to get to bed early. 

At least we've stopped things from going completely off-course, however, and can head into tomorrow (or our next coding session) with positive momentum.
___
**Total time spent coding today**: 

**Total time spent coding thus far in June 2019**: 

**Total lifetime hours of coding**: 