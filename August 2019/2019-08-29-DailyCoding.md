# Thursday August 29th, 2019 Daily Coding Journal
23:18 — Here’s what my day at the office looked like today:
```
7:50 - 8:00
Connected mouse 

Replaced keyboard batteries

Got water

8:00 - 9:00
Scrum meeting

Caught up on email/Chatwork

Read documentation and pseudocoded solution to reset password email

// First we take the email that the user submitted via the Redux form.
// Then we make a call to the API to verify that there is an account associated with that email.Y
// If no account is associated with that email, throw an error 'No account associated with that email.
// Otherwise, if there is an account associated with that email, create unique token ID and add it to database of active tokens.
// The token will use redux-saga race to expire after 24 hours, after the token has already been used, or after the user requests another token.
// Send the token link to the user's email.
// After the user clicks the link, token ID must be validated.
// If token ID is valid, UI loads a form that will enable to user to successfully reset their password.
// If token ID is not valid, user is informed that an error has occured, and to please re-enter their email to have another token sent to them.

NOTE: While my thinking was mostly right here, my team chose a slightly different implementation strategy.

9:00 - 10:30
Read MongoDB documentation and learned about methods that may be relevant to the forgot password task.

Read NODEJS API and JOI documentation

10:30 - 11:20
Redux-Saga flow and Joi discussion with team leader.

11:20 - 11:45 
Did some testing of the mobile app to confirm UI flow.

11:45-12:45
Lunch

12:45 - 1:00
Reviewed some code from the morning session.

1:00 - 2:00
HR Meeting

2:00 - 2:15
Clarified next step with team leader.

2:15 - 5:55
Built new UI for the password sent page (haven’t yet implemented functionality for the back arrow, or button yet however).

Cleaned up code from the forgot password page.

MongoDB NOTES:
In MongoDB documents are just collections of objects.

After creating a new database, the “show database” command will not show your newly created database.

The drop( ) method is used to remove all of the documents inside a collection.

The remove( ) method deletes both all of the documents and the collection itself.

Questions:
How can I overwrite Material UI’s hover effects?
(Ended up answering this one for myself after reading documentation)

Resources to look further into:

React-Router: https://github.com/ReactTraining/react-router/blob/master/packages/react-router/docs/api/history.md

Parse Platform: https://parseplatform.org
```
23:24 -- My girl surprised me with a visit tonight so I didn't get an evening coding session in. With that being said, I did stay almost an hour after work to get some extra React and Material UI practice in.

That along with the 5 or so minutes it takes to write this journal and commit it to GitHub takes me to the hour of extra practice outside work hours I like to reach each day :).

23:26 -- In any case, I need to get to sleep now. It's late and I don't want to be tired for tomorrow.
___
**Total time spent working as an employed developer today**: 8 hours

**Total time spent practicing coding outside of work today**: 1 hour

**Total time spent practicing coding outside of work thus far in August 2019**: 18 hours 41 minutes

**Total lifetime hours practicing code outside of a job**: 698 hours 21 minutes

**Total lifetime hours working as an employed developer**: 58 hours 51 minutes