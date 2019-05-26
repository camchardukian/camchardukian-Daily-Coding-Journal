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



___
**Total time spent coding today**:

**Total time spent coding thus far in May 2019**:

**Total lifetime hours of coding**:


