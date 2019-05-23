# Thursday May 23rd, 2019 Daily Coding Journal

22:59 -- Here we go... late start. It's not ideal, but I do have a goal to try to program for at least an hour everyday. I haven't failed to meet this goal for around a month now. Let's keep the streak alive!

23:11 -- I just finished watching the Forms Part I tutorial video. Now I'm going to practice recreating everything from scratch.

23:20 -- Not a bad start...

```
import React from "react"

class App extends React.Component {
    constructor() {
        super ()
        this.state = {
        firstName: ""
    }
    this.clickHandle = this.clickHandle.bind(this)
    }
    
    clickHandle () {
        console.log("changes")
    }
    
    render() {
        return (
        <form>
        <input type = "text" placeholder = "First Name" onChange = {this.clickHandle} />
        </form>
        )
    }
}

export default App
```

23:28 -- I've gotten about 30 minutes in now, but there's just no way I'm going to be able to get to a full hour of productive programming today.

However, if you count the time I spent creating my new programming Youtube channel and editing my [first video for the channel](https://www.youtube.com/watch?v=j23j1n0HNvI), then I did put a solid hour into making myself more marketable as a developer today.

In any case, I need to get to sleep now. I'm exhausted. Let's regroup and see if we can get going again tomorrow.
___
**Total time spent coding today**: 35 minutes
___
**Total time spent coding thus far in May 2019**: 15 hours 24 minutes

**Total lifetime hours of coding**: 550 hours 14 minutes