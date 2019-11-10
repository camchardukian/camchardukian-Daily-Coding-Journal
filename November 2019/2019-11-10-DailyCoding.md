# Sunday November 10th, 2019 Daily Coding Journal

17:58 -- Aaaaand we're back on the grind. I'm trying to put in an hour or so of practice in tonight. I've got a dream, let's take another step towards realizing it!

Tonight I'll work on FreeCodeCamp's React exercises.

18:11 -- I just finished a couple exercises. I'm so used to coding at work now and saving (cmd + s) to see my changes. Now, when I make a change on FreeCodeCamp and want to see the changes I'm still in the habit of using *cmd + s* and I keep accidentally trying to save files haha.

18:14 -- According to [this exercise](https://www.freecodecamp.org/learn/front-end-libraries/react/use-a-ternary-expression-for-conditional-rendering), ternary operators can be combined (chained?) together.

18:25 -- Here's some [follow-up documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator) I just read to understand the idea of chaining ternary operators together.

Basically, the colon character *':'* can be used as *else*, but also as *else if*.

18:41 -- I just finished a [cool exercise](https://www.freecodecamp.org/learn/front-end-libraries/react/render-conditionally-from-props) in which we programmed a very basic game. In the game we'd click a button, and we'd have a 50/50 chance of winning or losing the game.

Depending on the result, we'd either render, "You Win!" or "You Lose!" to the screen.

Here's what my code looked like:
```
class Results extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    const { fiftyFifty } = this.props
    return (
      <h1>
      {
         fiftyFifty >= 0.5 ? ("You Win!") : ("You Lose!")
      }
      </h1>
    )
  };
};

class GameOfChance extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      counter: 1
    }
    this.handleClick = this.handleClick.bind(this);
  }
  handleClick() {
    this.setState({
      counter: this.state.counter +=1
    });
  }
  render() {
    const expression = Math.random()
    return (
      <div>
        <button onClick={this.handleClick}>Play Again</button>
        { /* change code below this line */ }
<Results fiftyFifty={expression} />
        { /* change code above this line */ }
        <p>{'Turn: ' + this.state.counter}</p>
      </div>
    );
  }
};
```
19:06 -- I just finished an exercise on mapping through an array to render data. It was great to strenghten my knowledge on this as it's something I've had to do in many of the features on at work.

19:07 -- Well, I've already coded for more than an hour today plus taught 4 hours of English on my "rest day".

Let's take a break now, get some dinner, and get back on the developer life grind tomorrow! :D
___
**Total time spent working as an employed developer today**: N/A

**Total time spent practicing code outside of work today**: 1 hour 13 minutes

**Total time spent practicing code outside of work thus far in November 2019**: 11 hours 18 minutes

**Total lifetime hours practicing code outside of a job**: 775 hours 42 minutes

**Total lifetime hours working as an employed developer**: 455 hours 54 minutes
