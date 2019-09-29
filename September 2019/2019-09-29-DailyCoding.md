# Sunday September 29th, 2019 Daily Coding Journal

18:12 — I’m feeling a bit tired, but the responsible thing to do for tomorrow would be to familiarize myself with the tools I’m going to need for my next task at the office. So… here we go.

18:19 — Some of the new tools I’m going to be needing this week include axis post, form data, and react-image-crop. Let’s start with some notes on react-image-crop.

18:20 — React-image-crop is:
> An image cropping tool for React with no dependencies.

18:24 — Here are some of the benefits of using this library:
— Responsive (It’s possible to use either pixels or percentages)

— Compatible with touch devices.

— No dependencies.

— Min-max crop size.

18:26 — We can install this library with the following command:
> npm i react-image-crop --save

In the JS file we use this library, we import it as so:
> import ReactCrop from ‘react-image-crop’;

18:28 — This library is a bit unique because when using it we also need to import something into our CSS or SCSS file.

For my project at work I’m using SCSS files so I’ll do the SCSS import as so:
> import ‘react-image-crop/lib/ReactCrop.scss’;

18:33 — It looks like there are TONS of props available in this library. Some of the props are required. A few examples of required props for *ReactCrop* include:

— **src** — Our image url or path. 

— **onChange(crop, percentCrop)** — This is a callback function that fires every time our crop image is dragged/resized. Within this callback function we need to use *setState* (or I’d assume dispatching a Redux action that would eventually update state could also work, however, my intuition says that using Redux isn’t the way to go here).

— **crop** — an object that is basically the image that is being cropped. This object will include information like the size, width and the height of the image, how said image will be positioned, and possibly the aspect ratio of the image. By default, the crop object uses pixels but as a developer we could instead use percentages if we want our design to be more responsive.
___

18:40 — The majority of our props in react-image-crop are optional. Here are the optional props you may or may not find yourself using with this library.

(NOTE: I wrote these by hand… some [word-for-word from the documentation](https://www.npmjs.com/package/react-image-crop?fbclid=IwAR2g67AMwrCtwmGsIAHnVZPTYNnRvxA6ZbyKN58LXT0fy5OfAGDrBg-hzeQ) and some summarized in my own words).

Without further ado:

— **minWidth** — A minimum crop width, in pixels.

— **minHeight** — A minimum crop height, in pixels.

— **maxWidth** — A maximum crop width, in pixels.

— **maxHeight** — A maximum crop height, in pixels.

— **keepSelection** — If this prop is set to true, it seems that the user won’t be able to deselect the image by clicking outside the selection area.

— **disabled** — If this is set to thrue, the user won’t be able to resize or draw a new crop.

— **locked** — If set to true, the user won’t be able to resize or draw a crop. However… they *will* still be able to drag the existing crop around.

— **className** —A string of classes to add to the main ReactCrop element (From my understanding, this optional prop basically just allows us to add CSS classes to our ReactCrop element).

— **style** — Used for making inline style objects inside of our JSX code that will be passed to the *image’s wrapper* element.

— **imageStyle** — Used for making inline style objects that will be passed to our image element.

— **onComplete(crop percentCrop)** — This prop is a callback function which occurs after a resize, drag, or nudge occurs. This callback function passes the current crop state object to … ? (I don’t really understand what the intended use case is for this prop).

— **onImageLoaded(image)** — This is a callback function which occurs when our image is loaded. This callback can be useful if we want to set our crop based on the dimensions of the image the user is uploading.

— **onImageError(event)** — This prop will call the event passed to it if any error occurs while the image is being uploaded/loaded.

— **onDragStart(event)** —This prop is a callback which occurs whenever a user starts dragging or resizing.

— **onDragEnd(event)** — This callback occurs when a user releases their touch or cursor after dragging/resizing something.

— **crossorigin** — Allows setting the cross origin attribute on the image (I’m not really sure what this crossorigin image does, or why we’d need it.

— **renderSelectionAddon(state)** — This prop renders a custom element in crop selection. (Like I said before, I really don’t know the real-world use of a such a function.

— **renderComponent** — This prop allows us to render a custom HTML element tour page instead of an image. A good use case for the would be wanting to have your file uploading app to also be able tot support videos.

— **ruleOfThirds** — This prop if set to true will produce rule of thirds lines in our cropping area. This could help our users upload images in such a way that they are more likely to choose easily cropable images or crop their images in a way that is more visually appealing.

— **circularCrop** — This prop displays our crop area as a circle. If our image in the process of being cropped is not a square, our crop area will then be warped into an oval shape.
___

19:12 — Man oh man, I’m so beyond exhausted tonight. I’m feeling my eyes grow oh so heavy every 15 minutes in this coffee shop lol. I’ll have to subtract 10 minutes from this coding session when it’s finished hahahaha.

19:15 — Now that I’ve gotten a very, very basic overview of react-image-crop, I’m going to quickly take notes on formData. The following notes were mostly compiled from the [Mozilla Developer Network page on FormData Objects](https://developer.mozilla.org/en-US/docs/Web/API/FormData/Using_FormData_Objects):

— The FormData object lets us compile a set of key/value pairs to send using XMLHttpRequest.

— We can create a new FormData object like so:
> let myFormData = new FormData();

— We can “attach” or as programmers like to say, “append” additional fields to our FormData object using the *append()* method.

— Blob stands for binary large object.

—Usually we will use strings when appending things to our form data object. In the case of files, however, we will use Blobs.

— To create a Blob, we will invoke the *Blob()* constructor.

19:29 — Those are the very basics of FormData objects. Let me quickly look at the Axios post method, and then I’ll call it a night:

— So, the syntax for axios doesn’t look too complicated. To perform a post request using my example *myFormData* above, I guess at work tomorrow I’ll do something like this:
```
axios({
url: ‘/ourApiHere’,
method: ‘POST’,
authorization: ‘sessionToken’
data: myFormData
})
```
— I’d then need a .then() to consider what I’d want to do if the POST was successful and some error if the POST was not successful.

19:46 — Well, I wouldn’t say I’m an expert at any of the technologies I covered in this session, but at least I just got the basics of them down so that tomorrow I can hit the ground running or at least have some intelligent questions for my team leader.

___
**Total time spent working as an employed developer today**: N/A

**Total time spent practicing code outside of work today**: 1 hour 33 minutes

**Total time spent practicing code outside of work thus far in September 2019**: 31 hours 42 minutes

**Total lifetime hours practicing code outside of a job**: 732 hours 18 minutes

**Total lifetime hours working as an employed developer**: 212 hours 5 minutes