# Tuesday July 28th 2020 Daily Coding Journal

19:55 -- Today was a solid day. First, here's what I did at the office:

```
8:00 - 11:45
Daily standup meeting

Caught up on Slack/email

Had some downtime while others were reviewing my pull requests so I spent some time researching and taking notes on Axios

Started Implementing the ability for users to skip uploading a video in the student signup flow

11:45 - 12:45
Lunch/Nap

12:45 - 17:00
Finished implementing the ability for users to skip uploading a video in the student signup flow

Started working on a bug where the banner displays repeatedly if the user closes the app (probably need another 30 minutes or so tomorrow morning to be finished).

Resources:
Axios Crash Course: https://www.youtube.com/watch?v=6LyagkoRWYA

Axios: https://github.com/axios/axios

JSON Web Tokens: https://jwt.io/

List of HTTP header fields: https://en.wikipedia.org/wiki/List_of_HTTP_header_fields

How to clean a React Native project:
https://stackoverflow.com/questions/48018988/clean-react-native-project/48019133

GIT won’t add a modified file:
https://stackoverflow.com/questions/26049272/git-wont-add-modified-file

Don’t put constants everywhere:
https://medium.com/@programmerr47/dont-put-constants-everywhere-b3bb9cb0bbae

React Native dropdown alert: https://github.com/testshallpass/react-native-dropdownalert

React Native AppState: https://reactnative.dev/docs/appstate

Notes:
Axios is an HTTP client that can be used to make requests, add headers, etc.

The default method Axios uses is get.

We can gain access to Axios either via either its CDN or by installing it using NPM.

One example way we can make a get request using Axios is:
axios({
method: ‘get’,
url: “http://yoururl.com/maybesomeapihere”,
params: {
_limit: 5
}
}).then(res => console.log(res.data)).
catch(err => console.error(err));

We could also do the same with a shorter syntax like so:

axios.get(“http://yoururl.com/maybesomeapihere”, {params: {_limit: 5})
.then(res => console.log(res.data))
.catch(err => console.error(err));
}

The difference between PUT and PATCH requests is that PUT is usually intended to replaced the entire object while PATCH is usually intended for just changing some number of fields within a JSON object rather than the object itself.

We can use axios.all(), and pass this method an array of requests and all of the requests will be made simultaneously.

We can send HTTP headers using Axios by adding them as another argument to one of our HTTP requests. For example, we could write:

axios.post(‘https://someurlhere’, {ourDesiredParams},
{headers: {
‘Content-Type’: application/json,
Authorization: ‘example token’
})
.then(res => console.log(res.data))
.catch(err => console.error(err));
}

It is possible to cancel requests using Axios.

Axios interceptors can be used to log the requests we’ve made.

We can create axios instances using axios.create({ baseURL:
‘https:ourwebsitename/locationofourapis’
});

We can set timeouts to our HTTPS requests using axios so that the request will timeout if a response is not received after a certain number of milliseconds.
```

21:59 -- Today was one of those days where I felt like a "real developer". Though I didn't know all of the answers, I at least was able to ask the right questions.

Probably 90% of those questions were answerable by google. The other 10% were at least specific enough so that my teammates were immediately able to transfer the necessary knowledge to me.

20:01 -- Apart from my day at the office, I also spent an hour or so coding this evening. And... I'm super excited because tonight I finished the 2nd project in the FreeCodeCamp _APIs and Microservices_ curriculum!

20:03 -- Tomorrow, I'll start doing some research for the next project in the curriculum -- a URL shortener.
I really have no idea how to get started with this next project.

To be fair though, just a few days ago I had no idea how I'd get through the 2nd project in the curriculum.

I guess we just need to keepon putting the time in and we'll eventually get where we need to go! :D

---

**Total time spent working as an employed developer today**: 8 hours 8 minutes

**Total time spent practicing code outside of work today**: 1 hour 1 minute

**Total time spent practicing code outside of work thus far in July 2020**: 24 hours 37 minutes

**Total lifetime hours practicing code outside of a job**: 951 hours 2 minutes

**Total lifetime hours working as an employed developer**: 1886 hours 40 minutes
