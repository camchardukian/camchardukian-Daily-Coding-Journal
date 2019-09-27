# Friday September 27th, 2019 Daily Coding Journal

22:19 -- Here's what my day at the office looked like today:
```
7:50 - 8:00
Connected keyboard.

Connected mouse.

8:00 - 11:45
Scrum meeting.

Caught up on Chatwork/email

Continued working on settings page bugs.

11:45 - 12:45
Lunch/nap

12:45 - 3:55
Continued working on settings page bugs.

4:00 - 5:00
Read documentation and began planning how to implement solution to upload profile and background picture issue.

Notes:
— Anytime you add an event listener, you also need to remove that event listener when your component unmounts. If you fail to do this, it is possible to have duplicate event listeners on a page leading to poor performance, and possibly even an application crash. 

Example bad code below:
 componentDidMount() {
    window.addEventListener('scroll', this.listenScrollEvent);
  }





Example good code:
 componentDidMount() {
    window.addEventListener('scroll', this.listenScrollEvent);
  }



  componentWillUnmount() {
    window.removeEventListener('scroll', this.listenScrollEvent);
  }


— Use shift + enter for linebreak on Mac while using Chatwork.

— If we want our users to be enter a file instead of text, we’ll use <input type = “file> 

Note: If you intend to allow users to upload multiple files, you’ll need to add the *multiple* attribute.

— To upload a file we need to store it in state.

— Once our file is stored in state, we can send it to the server (possibly with axios)

Resources:

Good website for designing flow charts, diagrams, etc: https://www.draw.io/

Basic tutorial for uploading files with React and Axios.
```
22:21 -- As you can see, there were some pretty good nuggets of information I got today. After work, I played in a soccer match with some guys from my company.

It was my first time playing in probably 5 years. I played decent, but my body kind of hurts now. I'm an old man! lol

This weekend I'll try to learn more about uploading files with ReactJS and axios. For now though... I'm pretty beat. 

See you tomorrow!

___
**Total time spent working as an employed developer today**: 8 hours

**Total time spent practicing code outside of work today**: 9 minutes

**Total time spent practicing code outside of work thus far in September 2019**: 30 hours 4 minutes

**Total lifetime hours practicing code outside of a job**: 730 hours 40 minutes

**Total lifetime hours working as an employed developer**: 212 hours 5 minutes