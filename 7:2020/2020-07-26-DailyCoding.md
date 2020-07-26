# Sunday July 26th 2020 Daily Coding Journal

23:22 -- Today was a really solid day. I spent about 6 hours this morning teaching English classes (the workload today was heavier than normal as I had to administer and mark one the final exams of the students in my 2nd class).

23:24 -- In the evening, however, I started working on the 2nd project in FreeCodeCamp’s API and Microservices curriculum. This project entails getting a user’s IP address, their device’s preferred languages, and some information about their system such as their web browser and system OS.

Starting this project, I realized I didn’t know how to obtain any of these pieces of information. Fortunately, I found an [API for getting a user’s IP address](https://ip-api.com/).

After that, I realized I needed to learn a bit about HTTP. This is because it appears to be necessary to use HTTP headers in order to get a user’s device’s preferred languages and system information.

For example, I intend to use the [Accept-Language HTTP header](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Language) to get information about the user’s device’s preferred languages.

However, I’ve never spent a significant amount of time learning about HTTP. For that reason, I watched a Traversy Media HTTP Crash Course video.

Here are some of the notes I took while watching it:

---

- HTTP stands for Hyper Text Transfer Protocol.

- HTTP is a way for web servers to communicate with the client

- When we receive a response to our HTTP request, the response will contain two parts (a header and a body)

- While HTTP itself is stateless, we can use a variety of other tools (like our code, local storage, cookies, or sessions) to save the data we receive from the HTTP responses we receive.

- HTTPS stands for Hyper Text Transfer Protocol Secure

- HTTPS basically ensures any data sent is encrypted via SSL or TLS

- SSL stands for Secure Sockets Layer

- TLS stands for Transport Layer Security

- The 4 most popular HTTP methods are GET, POST, PUT, and DELETE

- Some of the most HTTP status codes include:

  - 200 - OK
  - 201 - OK created
  - 301 - Moved to new URL
  - 304 - Not modified (Cached version)
  - 400 - Bad request
  - 404 - Not found
  - 500 - Internal server error

- In Express we can use HTML inside of our res.send() method.

- We can send a status back to the client using res.status(our status number).send(‘our message here’). This could be useful for sending conditional error messages.

---

While watching the Traverse Media video I saw that if I use res.rend(req.header(‘name of your desired HTTP header here’)), I can receive a response that contains the information from said header.

I think that's going to come in handy while working on this second FreeCodeCamp project ;)

In any case, I'm exhausted. I'm going to get some rest. See you tomorrow!

---

**Total time spent working as an employed developer today**: N/A

**Total time spent practicing code outside of work today**: 1 hour 20 minutes

**Total time spent practicing code outside of work thus far in July 2020**: 22 hours 42 minutes

**Total lifetime hours practicing code outside of a job**: 949 hours 7 minutes

**Total lifetime hours working as an employed developer**: 1870 hours 31 minutes
