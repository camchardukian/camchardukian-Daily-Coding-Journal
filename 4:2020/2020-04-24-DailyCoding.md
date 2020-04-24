# Thursday April 23rd 2020 Daily Coding Journal

22:06 -- This morning at about 10am I realized that during discussions with my coworkers I had repeatedly said Firebase Firestone instead of Firebase Firestore. Oh well, you live and you learn hahaha ;)

Anyway, here's what I did for work today:
```
8:00 - 11:45
Daily standup meeting

Caught up on Slack/email

Research Firebase Firestone

11:45 - 12:45
Lunch/Nap

12:45 - 17:35
Created Firebase Firestore cloud database

End-of-sprint meeting

OKR meeting

Resources:

What is a NoSQL Database? How is Cloud Firestore structured? | Get to Know Cloud 
Firestore #1: https://www.youtube.com/watch?v=v_hR4K4auoQ

How do queries work in Cloud Firestore? | Get to Know Cloud Firestore #2: 
https://www.youtube.com/watch?v=Ofux_4c94FI&list=PLl-K7zZEsYLluG5MCVEzXAQ7AC
ZBCuZgZ&index=3&t=0s

Cloud Firestone Selecting Region to Store Data: 
https://stackoverflow.com/questions/48472534/cloud-firestore-selecting-region-to-store-data

Firebase Firestone V5 docs (using V5 as V6 doesn’t yet seem to have a decent solution for push notifications yet: https://v5.rnfirebase.io/docs/v5.x.x/firestore/android

Getting started with Cloud Firestore on React Native:
https://invertase.io/blog/getting-started-with-cloud-firestore-on-react-native

Flatlist: https://reactnative.dev/docs/flatlist.html


Notes:
A foreign key is something we use in relational databases if we need to include data from one 
table inside of another table.

Many developers like working with non-relational databases because doing so allows them to easily iterate on their database design such as by adding or changing fields without always having to worry about something else breaking.

Data normalization is the idea that each piece of data should only exist 1 time in your database.

One of the big drawbacks of using non-relational databases is that they often don't adhere to the concept of data normalization. As a result, there are many circumstances in which we will have to change the same data multiple times across different parts of the database. This brings the risk of accidentally forgetting or failing to change the data in some part of the database and then ending up with inconsistent data.

In short, many people feel that non-relational databases aren't the best for writing data to the
database, but they are excellent for reading data. Thus, for applications where instances of reading data greatly outnumber instances of writing data, non-relational databases may perform better than the traditional relational databases.

Cloud Firestore provides 2 ways of reading documents. The 1st way is through the use of the get() method which queries the collection once (a collection in Firestone is basically a container that groups a given set of documents). The 2nd way is through the use of the onSnapshot() method which allows subscribing to updates in the query results. In other words, this 2nd method of reading documents allows us to see any changes to our collection in real time.
```
22:12 -- I think tomorrow I'll read that book on OKRs that the CTO at my company recommended to us a couple weeks ago. Apart from that, the only other new thing I can think of is that we're expected to get back into the office again on Monday.

That'll be interesting. I feel I've become a slightly stronger and more independent developer this last month working remotely.

I'm very grateful to have gotten a fairly extensive experience working remotely so early in my career, and I'm looking forward to working remotely more often in the future.

Well, those are about all the thoughts I have for now. See you later!
___
**Total time spent working as an employed developer today**: 8 hours 35 minutes

**Total time spent practicing code outside of work today**: 12 minutes

**Total time spent practicing code outside of work thus far in April 2020**: 7 hours 3 minutes

**Total lifetime hours practicing code outside of a job**: 858 hours 37 minutes

**Total lifetime hours working as an employed developer**: 1344 hours 28 minutes