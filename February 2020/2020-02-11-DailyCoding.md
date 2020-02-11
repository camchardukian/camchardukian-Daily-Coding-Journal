# Tuesday February 11th 2020 Daily Coding Journal

23:33 -- Today was a solid day. Here's what I did at the office today:
```
8:00 - 11:45

Standup meeting

Caught up on Slack/email

Research asset linking and added custom fonts to React-Native project

11:45 - 12:45
Lunch/Nap

12:45 - 17:20

Starting researching native modules in React Native.

Implemented basic iOS native modules

Fixed a bug concerned invalid tokens.

Resources:

How to Use Custom Fonts in React Native (2019): https://www.youtube.com/watch?v=60XGVZffPeE

React-Native-Asset library: https://github.com/unimonkiez/react-native-asset#readme

Xcode multiple commands produce error: https://github.com/oblador/react-native-vector-icons/issues/1074

React Native modules iOS tutorial: https://www.youtube.com/watch?v=eVGkC5EpxlE

React Native modules iOS documentation: https://facebook.github.io/react-native/docs/native-modules-ios

Notes:

I found out that the custom fonts tutorial I was following the last few minutes at the office yesterday no longer works in 2020. 

We can use the “react-native info” command to see a lot of relevant information about what version of react-native we’re running, as well as information about our IDE, system, and the iOS/android SDKs.

I found using the “react-native link” command to be difficult to use and it also has many limitations (such as only being able to link fonts). As such, I found a library that’s not only more effective in linking our assets (it can link all asset types, including .mp3 files), but that also unlinks assets automatically rather than us having to manually delink things.
EDIT: My opinion on this changed an hour or two later.

You need to run “react-native link” inside of the assets folder, NOT the root folder of your project.

If you use “git add .”, it will only add the files inside of the current directory to GIT, which IS NOT necessarily all of the files in your project.
```
23:36 -- A solid day at the office, a new software developer advice video published, and a lot of running around the city to move into a new apartment -- your boy is exhausted now.

Especially given that the last week or so my sleep has been pretty rough because of the lousy mattress at the cheap apartment I was renting.

In any case, let's get some sleep and get ready for another day of coding tomorrow! :D
___
**Total time spent working as an employed developer today**: 8 hours 1 minute

**Total time spent practicing code outside of work today**: 20 minutes

**Total time spent practicing code outside of work far in February 2020**: 1 hour 26 minutes

**Total lifetime hours practicing code outside of a job**: 810 hours 42 minutes

**Total lifetime hours working as an employed developer**: 918 hours 48 minutes