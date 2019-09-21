# Saturday September 21st, 2019 Daily Coding Journal

19:29 — I’ve been quite tired today. With that being said, I’m still going to spend a little time learning about Postman tonight. Some of the senior developers at my work recommended using it.

19:34 — I’m watching [this series](https://www.youtube.com/watch?v=juldrxDrSH0&list=PLhW3qG5bs-L-oT0GenwPLcJAPD_SiFK3C&index=1
) on Postman. I already watched the first couple videos at the office earlier this week.

Tonight I’ll watch and take notes on another 5ish videos.

19:40 — Update… I’m going to go to the restaurant, eat, and take notes on the next 5ish videos in the course.

20:08 — It took longer than I expected to find an open restaurant that had tables that were comfortable for working. Normally I like to go to the Korean place at this time of night, but they were out of the curry dish I like so I’m back to the French beefsteak restaurant I’ve held a grudge on for like 3 years lol.

In any case, back to our regular *programming* ;)

20:09 — Here are my notes for [video 4 in this Postman video series](https://www.youtube.com/watch?v=BExXvMHi3mk&list=PLhW3qG5bs-L-oT0GenwPLcJAPD_SiFK3C&index=4):

— A collection in Postman is a group of API request that can be stored and saved in some logical arrangement.

— One possible use case of a collection is if all of our API requests need to use a certain form of authorization or they share a common variable. By using postman, we don’t have to repeatedly enter our credentials for each individual API request we make.

— We can create folders in our collections. This could be useful if for example we wanted to group all of our *GET* requests in one folder and *POST* requests in one folder.

20:20 — Here are my notes for [video 5 in Raghav’s Postman video series](https://www.youtube.com/watch?v=6LIsCggi3-g&list=PLhW3qG5bs-L-oT0GenwPLcJAPD_SiFK3C&index=5):

— A collection runner gives us some different options for how we control how our collections are run. When running a collection of API requests, we have the option of controlling:
1. Which environment our requests are run in.
1. The number of iterations or how many times they are run.
1. If we want any delay of time between our requests being made.
1. Which type of responses we want logged (all requests, failed requests, or no requests).
1. Any files we need to run the API calls.

— The collection runner gives us some good information like whether our requests were successful, the amount of time it took to receive a response, and how large the responses we received were (in bytes).

— The collection runner also has additional options like a summary, the ability to export our results as a .JSON files, or an option to run our requests again.

20:31 — Here are my notes for [video 6 in Raghav’s Postman video series](https://www.youtube.com/watch?v=ENNsL-XGLus&list=PLhW3qG5bs-L-oT0GenwPLcJAPD_SiFK3C&index=6):

—  Postman gives us the ability to use variables in our requests. To access our variables, we put them inside of double curly brackets within our API requests.

— There are different scopes available for our variables. We can make global, environment, or collection scoped variables.

— Postman has its own console (similar to the JavaScript console) which we can use to receive additional information about our API requests.

20:38 — Here are my notes for [video 7 in Raghav’s Postman video series](https://www.youtube.com/watch?v=OailyIx6vgk&list=PLhW3qG5bs-L-oT0GenwPLcJAPD_SiFK3C&index=7):

— Inside of the tests “tab” in Postman, we can write different tests or use the console.log() method to help us debug.

— To access the value of our variables we use the following syntax… *pm.variables.get(“Enter_Your_Existing_Variable_Name_Here”)*.

— Similar to JavaScript, we can also create variables within Postman by using the *let* keyword within the “tests” tab.

— To set the value of our variables we use a slightly different syntax than before… *pm.variables.set(“name_of_variable”, “value_of_variable”)*.

— If you want to get or set variables at the global or environment level, you can do so by slightly modifying the syntax from before. You’ll replace the keyword *variables* from before with the keywords *globals* or *environment*. For example… *pm.globals.get()* or *pm.environment.set()*.

20:50 — The restaurant is about to close so let me push this journal entry to GitHub, and then have some time to exercise and relax before bed.

___
**Total time spent working as an employed developer today**: N/A

**Total time spent practicing code outside of work today**: 50 minutes

**Total time spent practicing code outside of work thus far in September 2019**: 24 hours 12 minutes

**Total lifetime hours practicing code outside of a job**: 724 hours 47 minutes

**Total lifetime hours working as an employed developer**: 170 hours 6 minutes