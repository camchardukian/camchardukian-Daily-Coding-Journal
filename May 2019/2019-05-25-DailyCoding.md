# Saturday May 25th, 2019 Daily Coding Journal

12:28 -- Just finished 4 hours of hustling, now let's get some coding in.

12:31 -- I'm going to rewatch the forms part II tutorial on Scrimba and then write the code from the video by hand.

12:43 -- I'm tired because I started hustling early this morning, but I'm going to write all of the code from the video at least once to get my brain processing everything and start establishing some muscle memory regarding forms.

12:58 -- MAN that was a ton of writing. Over 100 lines of code lol. Anyway, when I come back I'll try to recreate the instructor's forms from scratch. See ya later!

___

20:14 -- I'm back. Let's get that coding hustle in!

20:18 -- Here's the code I wrote for my textarea element:

```
<textarea value="" onChange={this.handleChange}/>
```
Is this code "right"? I'm not sure to be honest. I'm not sure what I'm supposed to be doing with the value property. The onChange method I've confirmed works, but I'm feeling pretty sketchy about what needs to be done about what the value needs to be set to.

20:22 -- Based on the first couple minutes of the video, it seems like my code snippet from above is ok.

20:24 -- Here is my code thus far...
```
<input type = "checkbox" checked = {this.state.isAwake} />
```

20:25 -- Of course, what do we need to note about the above code? Because I've set the checked property based on the state of isAwake without at all modifying my handleChange function, I've essentially created a read-only input element.

20:27 -- Let me do a little bit of coding and some pseudocode to figure out how I can solve this problem...

20:29 -- Here's the beginning of my thought process:
```
handleChange(event) {
        const {name, value, type, checked} = event.target
        
        // If type equals checked do something
        // otherwise, do something else

        this.setState({
            [name]: value
        })
    }
```

20:38 -- So, I've gotten things to log to the console, but I can't figure out why I can't change my checkbox from checked to unchecked and vice versa. Here is the code I came up with:

```
    handleChange(event) {
        console.log("test")
        const {name, value, type, checked} = event.target
        
        type === checked ? this.setState({
            [checked] : value }) :         this.setState({
            [name]: value
        })

    }
```

20:39 -- I know using a ternary operator in the scenario above was a good idea, but I'm not sure what I should set the state to if the type of the input element is checked.

20:41 -- Ahhhh, it seems I've forgotten to use the name property inside of my checkbox element.

20:44 -- I also made a mistake in that my ternary operator was seeking to evaluate whether the type of the element was set to *checked* rather than checking if the type was set to *checkbox*.

20:51 -- I've watched the tutorial talk about checkboxes, copyied some of the code by hand, and played around with it a bit. Now let me try to reconstruct things from scratch.

21:05 -- I think I've gotten the hang of things now. Here's what I just finished producing:

```
    handleChange(event) {
const {name, type, value, checked} = event.target

type === "checkbox" ? this.setState({[name]: checked}) : this.setState({ [name]: value})
    }

<label>
<input type = "checkbox"
value = {this.state.isAwake}
name = "isAwake"
onChange = {this.handleChange}
/>
Are you awake?
</label>
```

21:09 -- It's been a good coding session. I'm going to take a break to walk and maybe meet my girl a bit now, and then I'll play with radio buttons, and select elements.
___
22:06 -- Let me be honest, fatigue is starting to set in. I just got back from a walk, and recording a video for my [daily developer Youtube channel](https://www.youtube.com/channel/UCRUPCpCWCL6Mr-0QWNje29Q).

22:08 -- Let's start playing around with radio buttons.

22:17 -- I've spent the last 10 minutes or so playing around with the radio buttons code. Now, let's try creating some radio buttons from scratch.

22:22 -- Radio buttons are pretty simple. I've gotten the hang of them already having just recreated the instructor's example from scratch:
```
      <label>
                <input type = "radio"
                name = "gender"
                value = "male"
                checked = {this.state.gender === "male"}
                onChange = {this.handleChange}
                /> Male
                </label>
                <br/>
                <label>
                <input type = "radio"
                name = "gender"
                value = "female"
                checked = {this.state.gender === "female"}
                onChange = {this.handleChange}
                /> Female
                </label>
```

22:26 -- I quickly skimmed the material for adding select elements to our forms in React. I'm going to take a quick break, gain a decent understanding of select forms, and then post the daily developer video/eat/shower/night routine/sleep.
___
22:40 -- Alright I'm back. Let's go practice building the select form.

22:53 -- I can't figure out what I'm doing wrong. I've gotten a surface level of functioning going in that I can select from amongst the different options within my select tags. What I'm having trouble doing, however, is actually changing the state of *favoriteAnimal*.
```
<label> Favorite Animal </label>
                <select onChange = {this.handleChange}>
              <option value = "cats" name= "favoriteAnimal"> Cats </option>
              <option value = "dogs" name="favoriteAnimal">  Dogs </option>
              <option value = "penguins" name = "favoriteAnimal"> Penguins </option>
              <option value = "horses" name = "favoriteAnimal"> Horses </option>
                </select>


                
                <h1>{this.state.favoriteAnimal} hello</h1>
```

In the above code hello will display, but I can't seem to get this.state.favoriteAnimal to display.

22:58 -- I thought that maybe the problem was that I didn't give my select tag a value of {this.state.favoriteAnimal}. Even after I tried making this change, however, my application remained broken.

23:01 -- It turns out the problem was that I forgot to give my select tags a name property. Once I did that my code started working fine.

23:02 -- After watching the instructor's implementation of the form, it seems it was unnecessary for me to give all of the select options their own individual name properties.

23:04 -- It's been a solid (though not EXCELLENT) day. Tomorrow I'll work on forms again and strive to do at least 2.5 hours of coding. Anyway, let's call it a day now and get some rest. I got over 20 hours of coding in this week! Let's shoot for a full 40 hours of coding in next week!
___
**Total time spent coding today**: 2 hours 19 minutes

**Total time spent coding thus far in May 2019**: 59 hours 14 minutes

**Total lifetime hours of coding**: 555 hours 8 minutes