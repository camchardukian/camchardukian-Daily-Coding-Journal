# Wednesday July 3rd, 2019 Daily Coding Journal

10:43 -- Let's get started. Yesterday I was getting confused a bit by stdin and stdout.

I think stdin means 'standard input' and stdout means 'standard output', but I'm not sure what specifically I'm supposed to be doing with these... "things" in Node.js.

10:54 -- Got a bit sidetracked. I added a README.md file to my Daily Coding Journal GitHub repository. Let's get back on task in learning about stdin and stdout.

10:56 -- My notes I've taken below are from [this video](https://www.youtube.com/watch?v=gQPhH0roJ9s):

* Stdin and stdout provide a way for us to communicate with a process while it is running.

* The console.log() method uses the stdout object to log messages to the console.

* We can write a message to the console using *process.stdout.write()*.

* We have to control line spacing ourselves when using stdout.

* Just like standard JavaScript, we can use variables inside of *process.stdout.write* by using backticks and the dollar sign.

11:15 -- Now that I've finished that video I feel like I've gotten a rough grasp of the basics of stdin and stdout in the context of Node.js now.

11:28 -- I went back to HackerRank to try to solve the problem I'd been having trouble with stdin and stdout on.

Now, my only issue seems to be that I can't figure out which variable the team at HackerRank stored the input for our function in.

Here's my current code:
```
function leftRotation(arr, rotations) {
    let splicedValue;
    for (let i = 0; i < rotations; i += 1) {
        splicedValue = arr.splice(0, 1).join("");
        arr.push(parseInt(splicedValue))
    }
    process.stdout.write(`${arr}`)
}

// leftRotation()
console.log(stdin)
```
11:29 -- If I call leftRotation with my own array and numbers it works fine and successfully writes what I need it to write to the console.

The only issue I'm having is trying to find the variable they've stored the various inputs inside of.

I need to do this in order to have a dynamic input and pass all of this problem's various user tests.

11:32 -- You'd think I'd be looking for stdin or inputStdin or something along those lines. I've tried both of them already, both unsuccessfully.

Stderr said those two "variables/things" were undefined.

11:55 -- I've reached out for help in the discussion section of HackerRank, as well as the FreeCodeCamp forum.

Hopefully someone will be able to tell me where I'm going wrong with this problem.

In any case, I'm going to take a break and go through my morning routine.

I should also quickly say hello to some family members that stopped by our house.


___
**Total time spent coding today**: 

**Total time spent coding thus far in July 2019**: 

**Total lifetime hours of coding**: 