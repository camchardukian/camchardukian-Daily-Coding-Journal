# Wednesday May 15th, 2019 Daily Coding Journal

8:45 — Let’s go!

8:55 — I’ve spent the last 10 minutes installing **Visual Studio Code** and the relevant extension for markdown (*auto open markdown preview*).

8:56 — Now, however, I realized, however, that I can’t figure out how to use VS Code so I’m going to have to watch another tutorial on VS Code lol.

8:57 — The following notes will be from [this video](https://www.youtube.com/watch?v=fnPhJHN0jTE).

8:59 — VS Code was developed by ~~ME~~ Microsoft, but is open-source and completely cross-platform.

9:01 — VS Code has some version control features natively integrated.

9:03 — In VS Code there a number of settings you can adjust. Editor font-size, auto-save frequencies (if you want to use this feature at all), tab size, word wrap, etc.

9:06 — VS Code has an integrated terminal.

9:08 — VS Code allows developers to run multiple terminals simultaneously. This can be great for Angular or React developers that need a dev server but still want to do other things while waiting (to be honest my understanding on this concept is a little shaky).

9:09 — Gotta go. See ya later!

___

12:28 — I’m back. I’m kind of sleepy, but let’s see if we can get 20 minutes or so in before my critical thinking skills are completely worthless lol.

12:30 — Visual Code Studio implements **IntelliSense** — which is a term that refers to a variety of code editing features such as code completion, parameter info, etc.

12:36 — Many programmers enjoy using **Emmet** inside of VS Code. What is Emmet? Emmet is a plugin for text editors (such as VS Code) that makes writing HTML & CSS more efficient.

You could for example type
> h1 (tab key)

instead of having to write standard HTML
```html
<h1> </h1>
```
Typing
> h1.test

with Emmet would produce the following HTML code
```html
<h1 class=“test”></h1>
```

These are a just a few amongst endless possible examples.

12:41 — In VS Code we can choose from and install dozens (if not hundreds) of different themes and extensions.

12:42 — I think I’m going to need to take a quick nap.
___

13:29 — I was out cold in the convenience store for like 45 minutes. Let’s get back to it.

13:33 — Apparently there’s an extension called **bracket pair colorizer** that will make our brackets different colors in order for us to more easily identify which brackets go with which in situations involving things like nested if statements.

13:42 — I’ve spent the last 10 or so minutes listening to explanations about some of the different popular VS Code extensions, as well as installing them. Here are a few examples:
* JavaScript (ES6) code snippets (Offers many shortcuts for writing ES6 code)
* Brackets Pair Colorizer (described above)
* vscode faker (useful in creating fake credit care numbers, addresses, etc for testing purposes)

13:52 — VS Code also has some features that make it easy to use with GitHub.

13:55 — When I come back I’m going to have to watch another tutorial. Despite that Traversy Media video on Visual Code studio being almost 40 minutes I have yet to figure out how to actually create and save new files in VS Code lol.
___

14:43 — Let’s get another 15 minutes in.

14:49 — I’ve figured out how to open, and save new folders and files now. But… I haven’t yet figured out how to get the auto open markdown preview extension working yet.

14:55 — It looks like I’ve got everything up and running now. Now I’m just going to have to review a little bit of the syntax from yesterday and go back to make everything pretty.
___

17:12 -- I've spent the last 10 minutes or so updating stuff on GitHub. Now I'm going to correct the formatting thus far in today's entry now that I have successfully set up VS Code and auto open markdown preview.

17:46 -- I went back and made everything pretty, and man... is it pretty. My friend was *sooooo* right about markdown being **super** programmer-friendly. Everything looks so much better now that I went and converted all of my plain text into markdown.

While there are a lot of cool markdown features I've already taken advantage of, these are probably my three favorite features of markdown thus far...
1. Code blocks
1. Horizontal rules 
1. Strikethroughs

The use of code blocks makes my journal entries significantly more readable.

Horizontal rules are a great way to indicate a time break between pomodoro sessions without me having to explain that I'm getting up from the computer to go do something else.

Strikethroughs are less useful than the previous two features, but I like how easily strikethrough features are to implement requiring just a few extra keystrokes rather than me having to resize my application window in Pages, highlight the text I want to perform a strikethrough on and then on top of all that still having to go find the strikethrough button.

17:57 -- Anyway, that's enough from me for now. See you tonight to get some more work done with React.
___
18:57 -- My concentration seems to be weakening a bit. I just finished eating dinner, but I figure I better get another pomodoro session in before my brain completely melts for the day haha

19:06 -- I'm excited to write some of my actual project code with markdown today.

19:13 -- Let's give markdown a shot here. Show this journal entry some love. Here's the current function I'm working on...
```javascript
  handleChange(id) {
        this.setState(prevState => {
            const finalTodos = prevState.todos.map(item => {       
            }
            ) // closing parentheses
        }
        ) // closing parentheses for setState
    }
```

19:19 -- Fast forward another five minutes and I've written code to log the completed value of all the items in their previous state.
```
handleChange(id) {
        this.setState(prevState => {
            const finalTodos = prevState.todos.map(item => {
                if (item.completed) {
                    console.log(item.completed)
                }
                else {
                    console.log(item.completed)
                }
            }
            ) // closing parentheses
        }
        ) // closing parentheses for setState
    }
```
19:20 -- While the above code isn't of much practical use, get ready. I have a good feeling we're about to throw a zinger at this problem that's been staring at my face for far too long.

handleChange(id) {
        this.setState(prevState => {
            const finalTodos = prevState.todos.map(item => {
                if (item.completed) {
                    item.completed = !item.completed
                }
                return item.completed
                
            }
            ) // closing parentheses
        }
        ) // closing parentheses for setState
    }


19:36 -- I'm just not getting anywhere with this problem, which is disappointing considering I've tried it so many times. Let's watch the video... **again**

19:39 -- I'm going to write the solution down again by hand, hopefully later tonight. For now though I've been pretty stretched to my limits and need a break
___
22:33 -- Too gassed to give it another go tonight. Fortunately, tomorrow I'll be able to focus on React again now that I've gotten down the basics of VS Code and markdown.
___

Total time spent coding today: 3 hours 9 minutes
___
Total time spent coding thus far in May 2019: 30 hours 42 minutes
___
Total lifetime hours of coding: 526 hours 36 minutes