# Thursday July 23rd 2020 Daily Coding Journal

23:25 -- Today was a pretty solid day. Here's what I did at the office:

```
8:00 - 11:45
Daily standup meeting

Caught up on Slack/email

Continued working on the booking history feature

11:45 - 12:45
Lunch/Nap

12:45 - 17:00
Continued working on the booking history feature

Resources:
React Native Navigation Params: https://reactnavigation.org/docs/params/

Notes:
```

23:26 -- I felt really burnt out this morning, but after about 9:30 or 10:00am I got into a groove for the rest of the day.

Today I felt like I gained a much deeper understanding of how React Native Navigation works.

23:28 -- After work I also spent about 50 minutes on FCC and 10 minutes reading _Practical Object-Oriented Design in Ruby_. The highlight of the evening was finishing the first backend project in FreeCodeCamp's API and Microservices curriculum. Here's a short snippet of the code I used in [my project](https://glitch.com/~fcc-timestamp-microservice-cameron):

```
app.get("/api/timestamp/", function (req, res) {
  const dateObject = new Date();
    const result = {"unix": dateObject.getTime(),"utc": dateObject.toUTCString()}
  res.json(result);
});

app.get("/api/timestamp/:date_string", function(req, res) {
  const date_string = req.params.date_string;
  const numbersOnlyRegex = /^\d+$/;
    const checkIfValidDate = (dateObject) => {
      const result = {"unix": dateObject.getTime(),"utc": dateObject.toUTCString()}
  if (result.utc === 'Invalid Date') {
    res.json({"error" : "Invalid Date" })
  }
  else {
    res.json(result)
  }
  }
  if (numbersOnlyRegex.test(date_string)) {
    const unixInteger = parseInt(date_string);
      const dateObject =  new Date(unixInteger);
    checkIfValidDate(dateObject)
  }
  else {
        const dateObject =  new Date(date_string);
        checkIfValidDate(dateObject)
  }
})
```

23:31 -- In any case, it's getting late now. See you tomorrow!

---

**Total time spent working as an employed developer today**: 8 hours 3 minutes

**Total time spent practicing code outside of work today**: 1 hour 5 minutes

**Total time spent practicing code outside of work thus far in July 2020**: 21 hours 13 minutes

**Total lifetime hours practicing code outside of a job**: 947 hours 38 minutes

**Total lifetime hours working as an employed developer**: 1862 hours 1 minute
