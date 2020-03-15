# Sunday March 15th 2020 Daily Coding Journal

14:51 -- Today I'm planning to learn a little bit about React Hook Form. Here are some of the notes I've taken on React Hook Form. Some of them were taken from [this video](https://www.youtube.com/watch?v=-mFXqOaqgZk), while other concepts were pulled straight from the [React Hook Form documentation](https://react-hook-form.com/get-started) itself.

We can install React Hook Form into our project using this command:
```
npm install react-hook-form
```
___
We can import React Hook Form into our component like so:
```
import { useForm } from 'react-hook-form'
```
___
In React Hook Form we need to register all of our inputs (I believe this is so that we can later validate them upon submission, but I'm still lacking some clarity on this).

We can do this using a "*ref*".

One thing I am absolutely clear on, however, is that it's just the inputs that need to be registered and not the submit button itself.
___
We can include a "required" attribute set to true. This will cause that input/field to be required in order for the user to submit the form. If the user tries to submit the form without having yet entered a value for some number of required fields, the user will be taken to the first required field that they have yet to fill out.

Likewise, we can also use a "minLength" attribute so that a given input/field demands a certain number of characters to be entered in order for that input/field's validation check to be passed.
___
React Hook Form provides an "errors" object to help us write logic for displaying error messages. We can access this error object like so:
```
const { errors } = useForm()
```
___
I think it's cool that React Hook Form has an errors object. It seems like in some cases this errors object alone may be enough for us to no longer need a separate validation file for error handling.
___
Async validation is also possible in React Hook Form by passing custom functions to the "validate" property. It seems that for general validation purposes like checking for maximum/minimum lengths async validation is unnecessary.

For more complex validation purposes, however, it may have some really strong use cases.
___
React Hook Form doesn't require us to rely on a state management system like Redux, but React Hook Form can be connected to Redux.
___
16:13 -- I just finished taking notes and getting my react hook form example project bootstrapped. Now I'm going to go walk around a bit to care for my body.

See you later!
___
20:55 -- I just finished another hour or so of coding. I finished a basic implementation of React Hook Form, and can confidently say that I am now comfortable with the basics of this form validation library.

20:57 -- It has been a pretty solid weekend of coding. Let's try to relax now and get some rest before another week of hustling! :D
___
**Total time spent working as an employed developer today**: N/A

**Total time spent practicing code outside of work today**: 2 hours 40 minutes

**Total time spent practicing code outside of work thus far in March 2020**: 8 hours 53 minutes

**Total lifetime hours practicing code outside of a job**: 835 hours 42 minutes

**Total lifetime hours working as an employed developer**: 1103 hours 50 minutes