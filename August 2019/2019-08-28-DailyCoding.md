# Wednesday August 28th, 2019 Daily Coding Journal
20:37 — Here’s what my day at the office looked like today:
```
7:50 - 8:00
Connected keyboard and mouse

8:00 - 8:30
Scrum meeting

Finished debugging challenge from yesterday by myself.

8:30 - 9:20
Caught up on Chatwork/Email.

Read some documentation about API calls.

9:20 - 9:35
Quick meeting with team leader to talk about clean coding practices.

Installed GitLens

Installed ESLint

9:35 - 10:25
Cleaned up code

10:25 - 11:00
Debugging + API discussion with team leader

11:00 -11:25
Company vision meeting

11:25 - 11:45
Read redux form documentation

11:45-12:45
Lunch

12:45 - 2:00
Studied Joi documentation and took notes.

2:00 - 2:45
Discussed destructuring, props, advanced Redux flow, and Redux-Saga API call semi-capstone task.

2:45 - 4:15
Worked on and eventually completed Redux-Saga API call semi-capstone task.

4:15 - 5:15
Read documentation about Redux form validation.




Notes:

Redux-Saga NOTES:
A daemon is a computer programming process that runs in the background.

toastr is an easy to customize JavaScript library non-blocking notifications.

A channel is an object used to send and receive messages between tasks. Messages are queued until an interested receiver requests a message. Receivers that have made requests are also queued until a message in available.

There are just a few methods that channels utilize:

take — Channel.take(callback)

put — Channel.put(message)

flush — Channel.flush(callback)

close — Channel.close( )
This method closes the channel which prevents any more puts from being allowed. 

Joi NOTES:
Joi is a data validation library for JavaScript.

The goal of Joi is basically to ensure that we process data, and then only accept the data that is accurate/valid.

Joi was designed for server-side scripts. Many developers recommend using Yup if you need to  validate objects on the front-end.

Joi.object( ) instantiates (which more or less seems to mean construct) a Joi schema object.

keys( ) is a Joi method that defines the rules/constraints for our schema.

If you only have one set of keys, you are not required to use the keys( ) method. However, by convention it’s still common to use the keys( ) method even if you only have one set of keys.

with( ) is a Joi method that is commonly used to test schema conditions.

without( ) is another Joi method commonly used to test schema conditions.

Joi.string().email() can be used to test whether the format of an email is valid.

Joi.validate() is a method that can be used to validate objects.

Redux Form Validation NOTES:
The recommended way to do server-side validation with redux-form is to return a rejected promise from the onSubmit button.


Questions:

What are non-blocking notifications?

What are END actions and END objects in Redux-Saga?
```

20:38 — To be honest, today I’ve been pretty exhausted. Last night I stayed up a bit late and in the last 8 days I’ve spent 63 hours coding. I’m hoping to get to sleep early tonight so that I can go into work tomorrow feeling refreshed.

20:57 — I just spent about 20 minutes watching a 3-part series on making API calls using React and Redux. Unfortunately, I didn’t really feel like I took much away from those videos.

21:04 — Too. Exhausted. I’m committing to GitHub, and then heading to bed. Any more reading or watching videos is just a complete waste of time at this point in time as my brain is just mushed.

The most productive thing I can do now is get to bed early. Sleep a couple extra hours, and be sure I’m fully ready to go for tomorrow.
___
**Total time spent working as an employed developer today**: 8 hours 10 minutes

**Total time spent practicing coding outside of work today**: 32 minutes

**Total time spent practicing coding outside of work thus far in August 2019**: 17 hours 41 minutes

**Total lifetime hours practicing code outside of a job**: 697 hours 21 minutes

**Total lifetime hours working as an employed developer**: 50 hours 51 minutes