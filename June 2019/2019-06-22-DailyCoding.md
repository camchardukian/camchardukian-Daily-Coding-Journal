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

See you in the morning!
___
**Total time spent coding today**: 

**Total time spent coding thus far in June 2019**: 

**Total lifetime hours of coding**: 