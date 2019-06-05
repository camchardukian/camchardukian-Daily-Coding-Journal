# Tuesday June 5th, 2019 Daily Coding Journal

17:45 -- From about 2pm-3pm today I pair programmed with a Vietnamese "fresher" developer. In Vietnam, fresher is basically a term that means someone is hirable, but that they are a low-level junior developer.

In other words, their level is probably higher than what we would refer to as an intern in the US, but a bit lower than a fully fledged junior that's been on the job for 6+ months.

Anyway, even with his help, we were still unable to configure my first React app. We both got frustrated and couldn't progress past the error that's left me stuck the last several days. 

Let me try to look at the bright side, however, as the last few days have been so frustrating.

Today I learned:
* How to use [Teamviewer](https://www.teamviewer.com/en/) (to screenshare with the other dev).
* Internalized the benefits of pair programming (despite being unable to actually solve the problem, watching the other dev operate gave me some ideas for other things to try. I was also motivated and encouraged by the other dev's persistence even in the face of repeated failures).

In any case, I'm taking a break from banging my head against the wall.

18:15 -- I've gone to [hackerrank](https://www.hackerrank.com), created an account, and started doing algorithms there.

18:29 -- Solved the first algorithm, and starting getting familiar with using sublime-text.

When I get back from my break I'll solve another few algorithms, save the solutions, create a new GitHub repo and start commiting them.
___
19:45 -- I took a walk and had dinner. Let's solve the next algorithm on hackerrank! 

19:48 -- As of now, my rank on hackerrank is 1290536. Let's see how much it improves after solving another algorithm or two.

19:50 -- I'm now working on the *Compare the Triplets* algorithm. Basically, this algorithm gives you two arrays.

Each array represents a person's score in some event or category. If person A scores higher, we should give them a point.

Otherwise, if person B scores higher we should give person B a point.

So, for this problem we're going to need a function that takes in two parameters:

```
function compareScoreArrays (a, b) {

}
```

The two arguments passed to this array should be arrays.

19:55 -- Now, I'm trying to figure out what should be next. I don't know if it's the most optimal way, but I think we can create a doable solution using a plain old for loop.

19:59 -- Even before adding the for loop, I just thought that it would be important to note if our two passed arrays were of different length.

Obviously, it wouldn't be a valid comparison if one person competed in 10 events and another only competed in 2.

In other words, my version of the solution will only compare two people (or two arrays) of an equal length. Here's my example code below:
```
function compareTriplets(a, b) {
if (a.length === b.length) {
  console.log("arrays are same")
}
else {
  console.log("Your arrays are of different lengths.")
}
}

compareTriplets([1, 2, 3, 4], [3, 2, 1])
```

20:03 -- The next thing I have to focus on is adding some functionality. In the above code I only log to the console.

20:07 -- Added some variables, and a for loop:
```
function compareTriplets(a, b) {
if (a.length === b.length) {
  let aScore = 0;
  let bScore = 0;
  for (let i = 0; i < a.length; i++) {
    console.log(i)
  }
}
else {
  console.log("Your arrays are of different lengths.")
}
}

compareTriplets([1, 2, 3,], [3, 2, 1])
```

20:11 -- I've completed the challenge it seems. Here's what I've created thus far:

```
function compareTriplets(a, b) {
if (a.length === b.length) {
  let aScore = 0;
  let bScore = 0;
  for (let i = 0; i < a.length; i++) {
    if (a[i] > b[i]) {
      aScore++
    }
    else if (a[i] < b[i]) {
       bScore++
    }
  }
      return [aScore, bScore]
}
else {
  console.log("Your arrays are of different lengths.")
}
}

compareTriplets([1, 2, 3,], [3, 1, 5])
```
Let's just test it in hackerrank before we go over it...

It was successful! Now let's discuss what we did.

First we have a function that takes two parameters:
>function compareTriplets(a, b) { }

The two arguments passed to this function should both be arrays.

Then we create an *if statement* to see if our two passed arrays are of equal length.
> if (a.length === b.length)

Obviously we cannot do a proper direct comparison on our arrays (or people) if the arrays are of different lengths (or the people competed in a different number of events/categories.)

For that reason our else statement simply logs an error message to the console:
```
else {
  console.log("Your arrays are of different lengths.")
}
```
Now, if our arrays are of the same length, we'll process to the if clause rather than the else clause of our if statement.

While you could have done this step using a single variable by initializing a variable to an array as such:
> let scoreArr = [0, 0]

I opted to use multiple variables as I thought having multiple variables would require less bracket notation and be easier for new developers to understand:
>   let aScore = 0; let bScore = 0;

From there, I created a for loop that would iterate just enough times to go through the entire array:
```
for (let i = 0; i < a.length; i++) {
}
```
On each iteration of the array, we checked to see if a[i] was less than or greater than b[i]. In other words we first checked it a[0] was greater than b[0], then a[1] and b[1] and so on until we'd iterated through the entire length of the array.

Each time a was greater than b, we incremented our aScore variable by one:
```
if (a[i] > b[i]) {
      aScore++
    }
```
We also did the same for our bScore when b was greater than a:
```
else if (a[i] < b[i]) {
       bScore++
    }
```
After we finished iterating through everything we returned an array that included our aScore variable and our bScore variable:
> return [aScore, bScore]

And that folks is your answer for how I solved this algorithm!

How could we have made it better? For one, I think it could have been beneficial to specify what happens if a user's array contained objects, booleans, strings, or other non-number values.

We also could have used a single variable for our player's scores instead of having two variables.

Overall, however, I think this solution is very decent.

In any case, I'm feeling tired out now from all that typing. I'm going to take a break from all this code!

P.S. I'm having a lot of fun solving these algorithms. Much more fun than React has been the last few days hahahaha!
___
22:08 -- I'm back home now. I'm going to make a GitHub repo for the algorithms I've solved thus far.

22:57 -- Setup the github repo, added some additional explanations, reviewed the reduce methods, and made all my commits to the repo. It was a good session! 

22:58 -- I'm going to take a quick break, and then I'll create a video about the first algorithm for the [daily developer channel](https://www.youtube.com/channel/UCRUPCpCWCL6Mr-0QWNje29Q)!

___
**Total time spent coding today**: 3 hours 50 minutees

**Total time spent coding  thus far in June 2019**: 11 hours 17 minutes

**Total lifetime hours of coding**: 582 hours 36 minutes

