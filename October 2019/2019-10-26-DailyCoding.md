# Saturday October 26th, 2019 Daily Coding Journal

20:50 — It’s been a long week of work. I’ve already worked for 56+ hours this week. 48 or so programming at the office/learning code on my own time, and another 8 or so hours teaching English. As such, I’m feeling pretty tired.

I’m going to aim to get to bed early tonight. Before that, however, I’m going to start reading a book the director at my company recommended *The Art of Readable Code: Simple and Practical Techniques for Writing Better Code*.

I figure, because I’m feeling pretty fatigued, this is a way to continue to improve my abilities as a developer without overexerting myself when I’m already exhausted.

Let’s start reading…

## Chapter 1 -- Code Should Be Easy To Understand

The very first concept the authors introduce is that:
> Code should be easy to understand.

*How do we define code that’s easy to understand?* Well, the authors (Boswell & Foucher) propose that the definition of code that is easy to understand can be measured by how long it takes our average colleague to understand our code.

One objection many people have to this (and that I may have previously agreed with), is that it doesn’t matter if others can understand our code if we’re working on a one person project.

Boswell & Foucher refute this claim, however, by pointing out that it’s worth pursuing making our code easier for others to understand even on one-man projects because 6 months later, our own code is likely to look unfamiliar to us.

Another interesting concept is the idea of making our code short. I’ve always strived to refactor my code for brevity.

This is a good starting point as a 500 line file is likely to take less time to understand than a 2000 line file.

Boswell & Foucher suggest, however, that while trying to write fewer lines of code is a good goal, the benefits attained from adding comments to our code or spreading overly complex logic from one line to 2 or more lines often outweighs simply trying to have the shortest code possible.

Here’s another takeaway I really liked from this chapter. The authors said that if you are a programmer that has a compulsive need to fix any code that isn’t perfectly factored, there’s a simple question you can ask yourself to determine whether it’s time to move on to the next piece of code.

That question is… *Is this code easy to understand?* If so, it’s probably alright to move on. If not, it’s likely worth investing some time now to make the code more readable and avoid accumulating technical debt that will later need to be paid off.


## Chapter 2 -- Packing Information Into Names

The key idea Boswell & Foucher open this chapter with is developers should:
> Pack information into your names.

While it’s not really an epiphany for me, I like that the authors make the analogy of a variable, function, or class name being a lot like a mini comment.

While names don’t give us a ton of space to work with, they still have the potential to convey a lot of information.

**Concept #1**

The first actionable step we can take to improve our variable/function/class naming abilities is to use words that are very specific.

The authors give an excellent example using a function called *Stop()*. While *Stop()*, kind of gives you the idea of a what a function may do, renaming our function to *Kill()* or *Pause()* may more clearly express whether we would later be able to resume a process or not.

**Concept #2**
Boswell & Foucher suggest that in general we should avoid using generic names like *retvalue* or *foo*. Many developers use generic variable names because they can’t immediately think of anything better.

In the case of variables, we should drive to use names that describe the value(s) our variable(s) contain. By spending an extra few seconds naming our variables, we can save significantly more time down the road debugging our code.

**Concept #3**
Developers should strive to prefer concrete names over abstract names. In other words, we should aim to make our names describe precisely what our functions do, rather than the circumstances in which the function is used or the results of running the function.

**Concept #4**
Because readers will see a variable’s name every time said variable is used, we should try to include any information that’s very important to know inside of the variable’s name.

Here’s an example of my own I just came up with after reading some of the authors’ ideas.

Instead of naming a variable *id*, we may opt to name the variable *numberId* to help the reader of our code remember that the format of the variable needs to be a number data type rather than a string.

**Concept #5**
If our variables are measurements, it can be very helpful to include the unit type into the variable’s name. For example, delayedDispatchAction could be renamed delayedDispatchAction_ms.

This would inform the readers of our code which unit type (in this case milliseconds) that we were using.

Explicitly naming our variables and describing their data types can also be important for security purposes.

For example, instead of naming a variable *password*, we could name the variable *unsafePlainTextPassword* before it is encrypted.

**Concept #6**
There are a couple things we should consider when deciding how long our variable names should be. The first is that if a variable has a narrow scope, you can probably get away with giving the variable a shorter name because the reader is likely to be “closer” to the code, and seeing exactly how it is being used in context.

Should we use abbreviations or acronyms when naming? Boswell & Foucher suggest that it’s fine to use general programmer abbreviations like ‘string —> str’, or ‘evaluation —> eval’.

They seem to argue against using project-specific abbreviations in most cases, however.

As such, their general guideline is that if a new team member could understand your abbreviation, the name is probably fine. If not, you should probably refactor your code to use a clearer name.

Finally, also consider using formatting to convey meaning in your naming efforts. In JavaScript for example, constructor functions by convention should start with a capital letter while regular functions start with lowercase letters.

22:23 -- I just finished reading, and taking notes on the first two chapters of the book. It's been a solid, though not exactly mind blowing read thus far.

In any case, I surprised myself by spending over 1.5 hours reading/writing when I came into this session thinking I was exhausted.

I just created a new GitHub repo that I'll use for taking notes on the different software development books I read.

For now though, I'm going to commit this entry to GitHub and then get to bed.
___
**Total time spent working as an employed developer today**: N/A

**Total time spent practicing code outside of work today**: 1 hour 36 minutes

**Total time spent practicing code outside of work thus far in October 2019**: 25 hours 32 minutes

**Total lifetime hours practicing code outside of a job**: 758 hours 41 minutes

**Total lifetime hours working as an employed developer**: 374 hours 55 minutes