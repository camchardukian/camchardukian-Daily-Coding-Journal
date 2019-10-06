# Sunday October 6th, 2019 Daily Coding Journal

20:14 — Like I said yesterday, I’m going to try to rebuild my simple application from yesterday from scratch in order to internalize my understanding of how a child component can call a parent component’s method.

20:36 — I’ve successfully rebuilt my application from yesterday from scratch and have gotten more comfortable with the basics of giving a child component the ability to call a method form a parent component via props.

20:37 — Now, however, I’d like to extend things a little bit further and add props to my child method so that we could change the output that different children components have. For example given a “say hello to name prop” one child component might say hello to John while another child component could say hello to Sally.

21:01 — So I’ve built what I wanted to built using the child as a functional component. For a better understanding, however, I’ll see if I can also make things work if the child is a class component.

21:03 — Oh wow, converting things was way easier than I expected. All I had to do was change *props* in my ex-functional component to be *this.props* in my class component.

21:16 — Just for good measure, I deleted everything and rebuilt my mini-app from scratch. I’m definitely not a world-class expert on props (or anything in React for that matter), but I’m a lot more comfortable with this topic than I was at the beginning of the weekend. It’s good going in to work tomorrow knowing that I was better than when I left on Friday.

Anyway, for good measure here’s what my code ended up looking like…

ExampleChild: 
```
class ExampleChild extends React.Component {
    render() {
        console.log(this.props)
    return (
    <div>
        <button onClick={() => this.props.sayHello('john')}>hry </button>
    </div>
    )
    }
}

export default ExampleChild;
```
ExampleParent:
```
import React from 'react'
import ExampleChild from '../../Components/ExampleChild/index.js'

class ExampleParent extends React.PureComponent {
    
     sayHello = (name) => {
        alert(`hello ${name}`)
    }

    render() {
        return (
            <ExampleChild sayHello={this.sayHello} />
        )
    }
}

export default ExampleParent
```
Again, it’s no masterpiece, but with each React fundamentals weakness or blindspot I remove, I’ll become both a better and faster developer.

In any case, I’m going to call it a day, eat dinner, and then get ready for tomorrow.

See you then!

___
**Total time spent working as an employed developer today**: N/A

**Total time spent practicing code outside of work today**: 1 hour 13 minutes

**Total time spent practicing code outside of work thus far in October 2019**: 6 hours 41 minutes

**Total lifetime hours practicing code outside of a job**: 720 hours 20 minutes

**Total lifetime hours working as an employed developer**: 252 hours 49 minutes

