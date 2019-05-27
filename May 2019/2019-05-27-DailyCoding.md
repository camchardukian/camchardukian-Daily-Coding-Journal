# Monday May 27th, 2019 Daily Coding Journal

0:00 -- Yesterday I only got 46 minutes of code in. Let's make today a better day!

0:04 -- I'm going to shoot for completing the travel form before going to sleep tonight.

0:07 -- Right now I'm working to implement the select tags.

0:09 -- Here's where I'm at thus far:

```
<select>
<option> Bangkok </option>
<option> Ho Chi Minh City </option>
<option> Chiang Mai </option>
<option> Bali </option>
<option> Singapore </option>
</select>
```

0:16 -- Not sure why my code isn't working thus far. I can toggle from one destination to another but my state isn't changing...

```
<select>

<option name = "destination" value = "Bangkok" onChange = {this.handleChange}> Bangkok </option>

<option name = "destination" value = "Ho Chi Minh City" onChange = {this.handleChange}> Ho Chi Minh City </option>

<option name = "destination" value = "Chiang Mai" onChange = {this.handleChange}> Chiang Mai </option>

<option name = "destination" value = "Bali" onChange = {this.handleChange}> Bali </option>

<option name = "destination" value = "Singapore" onChange = {this.handleChange}> Singapore </option>

</select>
```

0:19 -- Unrelated note: While I knew you could indent multiple lines of code in VS Code by highlighting them and pressing tab, I also just realized that you can unindent multiple lines of code by highlighting them and pressing shift + tab simultaneously.

0:27 -- It turns out I should've been applying the name and clickhandle function onto the select tag instead of the individual options. Here's my working code:

```
<select value = {this.state.destination} name = "destination" onChange = {this.handleChange}>
<option value = "Bangkok"> Bangkok </option>
<option value = "Ho Chi Minh City"> Ho Chi Minh City </option>
<option value = "Chiang Mai"> Chiang Mai </option>
<option value = "Bali"> Bali </option>
<option value = "Singapore"> Singapore </option>
</select>
```

0:28 -- I'm going to take a 5 minute break now before finishing the checkboxes and getting to bed.
____
0:34 -- I'm back.

0:36 -- I'm off to a good start lol.

```
<input type = "checkbox" />
```

0:43 -- I'm writing some pretty wack cowboy code right now lol. I think I'm going to have to go rewatch the video about implementing checkboxes into our React forms to clean my code up.

0:47 -- Here's my seemingly functional, though ugly code before I go back and look at how the "proper" way of doing things is:
```
 handleChange (event) {
        const {name, value, type, checked} = event.target
        console.log("hello")
        type === "checkbox" ?
        this.setState({[name]: checked})
        : this.setState ({
            [name]: value
        })
    }
```
and...
```
<br />
<label> Dietary Restrictions </label>
<br/>

<input type = "checkbox" checked = {this.state.vegan} onChange = {this.handleChange} />
<label> Vegetarian </label>
<br/>
<input type = "checkbox" checked = {this.state.vegan} onChange = {this.handleChange} />
<label> Peanut Allergy </label>
<br/>
<input type = "checkbox" checked = {this.state.vegan} onChange = {this.handleChange} />
<label> Gluten-free </label>
<br/>
```

1:07 -- I finally got through everything. Here's my code... Wait a second. I'm having a bizarre bug on Scrimba where it won't allow me to copy and paste things O_O.

1:12 -- I tried to reload a saved version of my code in Scrimba, but in the end my code I'd been writing in this session just got lost. Guess this shows why it's important to use git and push frequent commits on your projects.

1:13 -- In any case, I'm going to eat a snack, shower, and get to bed. I also have to edit and post the video to my daily developer channel. I'll watch the practice video tomorrow to see how the instructor and I approached the airlines form differently.
___

23:01 -- Today has been kind of a meeeeh today. I stayed up late last night, and didn't sleep in enough this morning. As a result, I went through the day tired, and wasted a lot of time.

While I did earn some cash, exercise, and shave my head, I didn't get any additional programming in until now. Let's run through this code until at least midnight now!

23:03 -- I'm going to watch how the instructor implemented forms differently than myself. Then, I'll continue in the course.

23:05 -- One thing I immediately noticed is that when the instructor initialized state in his constructor function, he didn't create individual properties for each dietary restriction. Instead, he created a general *dietaryRestrictions* property and initialized it to an empty array.

UPDATE: He later switched from an array, to an object with each dietary restriction written as a key, and given a value of a false (because in this case we don't want any dietary restrictions checked by default). Example code from the video below:

```
dietaryRestrictions: {
isVegan: false,
isKosher: false,
isLactoseFree: false
}
```

23:11 -- The instructor likes to nest his radio buttons inside of *label* tags because doing so allows the user to not only select a radio button by clicking the radio button itself, but also allows them to select a radio button by clicking the label text associated with said radio button.

23:16 -- When using select tags, the option chosen by default does not update state unless you toggle from the default value to another value, and then back to the default.

A nice little trick I picked up from watching the instructor is that we can avoid this issue by creating our first option (which is automatically the default), making it valueless, and then prompting our users to choose one of the other values.

Example code from the video below:

```
<select 
value={this.state.destination} 
name="destination" 
onChange={this.handleChange}
>
<option value="">-- Please Choose a destination --</option>
<option value="germany">Germany</option>
<option value="norway">Norway</option>
<option value="north pole">North Pole</option>
<option value="south pole">South Pole</option>
</select>

```

23:25 -- The instructor and I used mostly the same logic throughout our ternary operators.

23:32 -- I've finished the video on forms and will now watch a video on "container/component architecture. The first time I'll just watch the video all the way through. Then, I'll watch it again while taking notes.

23:40 -- It seems container/component architecture is basically a method for structuring our code by separating our business logic and display logic.

This increasing our understanding of our code by reducing the amount of scrolling we have to do and compartmentalizing our code.

23:43 -- Let's get to the notes from [the video](https://scrimba.com/p/p7P5Hd/cwRZ9fG).

23:45 -- There's been a study that shows a programmer's ability to understand the code they're looking quickly diminishes as the file they're viewing requires more and more scrolling.

23:46 -- UI logic is sometimes referred to as rendering logic.

23:47 -- Business logic is the logic that mandates how the rendering logic changes.

23:48 -- A few years ago an idea emerged of having a presentational component ("dumb component") in charge of rendering elements to the page and another component that's in charge of the business logic ("smart component").

23:50 -- To make things as clear as possible, the smart component contains state and the methods influencing state while the dumb component is merely responsible for rendering the elements and presenting them on the page.

23:53 -- I just read a [medium article written by Dan Abramov](https://medium.com/@dan_abramov/smart-and-dumb-components-7ca2f9a7c7d0) (one of the primary developers of the React framework), in which he says that he now rarely uses smart and dumb components. He seems to have largely replaced his usage of them with React Hooks (which I don't yet know anything about but I'm sure I'll learn about in the coming weeks).

23:58 -- The instructor says that with the use of Redux, amongst other things, the divide of business logic and presentational components is not as prevalent as it once was.

___
**Total time spent coding today**: 2 hours 11 minutes

**Total time spent coding thus far in May 2019**: 62 hours 13 minutes

**Total lifetime hours of coding**: 558 hours 7 minutes


