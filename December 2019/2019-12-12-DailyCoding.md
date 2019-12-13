# Thursday December 12th, 2019 Daily Coding Journal

21:09 -- Today was a solid day at work. I feel like I'm saying that just about everyday now hahaha.

I'm gradually getting better at debugging the underlying causes of bugs in our applications.

Today I found a bug that was caused by a fetchMetaData Url not having an objectId and because of this I eventually figured out that my Redux form's initial values could not get updated properly in the way I wanted so I used getDerivedStateFromProps to take the previous values and still apply them to the initial values.

This allowed me to see if a video's objectId already existed in the database, even if the user tried to edit the video and fetch new metaData. Thus, I was able to successfully call the edit video function instead of the create new video function.

Anyway, here's what the rest of the day at the office looked like:
```
8:15 - 11:45
Connected keyboard.

Connected mouse.

Caught up on Chatwork/email

Working on fixing a number of misc. bugs

11:45 - 12:45
Lunch/nap

12:45 - 5:45
Working on fixing a number of misc. bugs

Resources:

Notes:
```
21:16 -- Tomorrow is the end of the current sprint so it should be a relatively light day of work. In any case, I still need my rest so I'm going to get ready for bed and see you tomorrow! :D
___
**Total time spent working as an employed developer today**: 8 hours 5 minutes

**Total time spent practicing code outside of work today**: 37 minutes

**Total time spent practicing code outside of work thus far in December 2019**: 7 hours

**Total lifetime hours practicing code outside of a job**: 796 hours 44 minutes

**Total lifetime hours working as an employed developer**: 650 hours 16 minutes