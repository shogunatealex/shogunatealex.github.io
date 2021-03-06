## Running this file

If you want to run this project just open index.html in any broswer that you like. From there you will be able to navigate the website!


To get started, check out the repository and inspect the code.

### Getting started

#### Part 1: Optimize PageSpeed Insights score for index.html


1. CSS
	* The style sheet was small so I moved all of it into the HTML document. This wouldn't be preferred if it was much longer but for such a simple site there is not need to make a request to another style sheet
	* Created a media query so that print.css is only called if the media type is print.
	* Removed the call to the google font, instead opted to download the font and link to it locally. That saves a trip to the google server while still maintaing the font.
	* Removed unnecessary CSS rules. There were a couple that I could find and consolidate.

2. JS
	* Minified the perfmatters.js script.
	* made the google analytics script run asynchronously

3. Images
	* Optimized all the images using Photoshop save for web feature.
	* Reduced the size of the pizzeria from 2K to 720P, then created a thumbnail that was even smaller for the main page.
	* Downloaded the pictures locally so that they wouldn't need to call a server every time. This reduced the CRP.



#### Part 2: Optimize Frames per Second in pizza.html

1. Stop FSL
	* Stopped the FSL when the Pizza's change size. Got it to under 1ms.

2. Stop Jank for with FPS
	* Got Pizza moving function down to under 1ms per frame. This is down from the 14-17ms before. I determined that the Math.sin is an expensive function and only has 5 differnet values. So I precalculated those and put them into an array before the for loop. This way it is only caluclated 5 times per sesion instead of being called for every single pizza item. This massively reduced the time to generate each frame.
