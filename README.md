# Website Performance Optimization portfolio project

The challenge: optimize this online portfolio for speed! Optimize the critical rendering path and make this page render as quickly as possible by applying the techniques learned in the [Critical Rendering Path course](https://www.udacity.com/course/ud884).

## Getting started

###Part 1: Optimize PageSpeed Insights score for index.html

**The Goal**: a Google PageSpeed Insights score of 90 or higher for mobile and desktop.

The live page can be viewed at [mobile-portfolio.firebaseapp.com](https://mobile-portfolio.firebaseapp.com/). Copy the URL and paste it in the analyze field at [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/) to view the scores.

#### Optimizations

- Resize and compress all images
- Inline all css styles for above the fold contend and defer loading of external css files
- Asynchronous or deferred loading of Javascript files

#### Additional Customizations

- Change content of page to a Doctor Who fanpage (for fun!)
- Change images to match new content
- Change header to include a CSS background image

###Part 2: Optimize Frames per Second in pizza.html

**The Goal**: Page renders at 60 frames per second when scrolling, the pizza size slider resizes pizza images in under 5ms.

The live page can be viewed at mobile-portfolio.firebaseapp.com/views/pizza.html](https://mobile-portfolio.firebaseapp.com/views/pizza.html) Open the page in Chrome and use devTools to record a timeline trace of scrolling and changing the pizza sizes with the slider. The trace will show the frames per second for scrolling. The console will also display information about the frame generation rates.

#### Optimizations

Changes made in [views/js/main.js](https://github.com/baker-natalie/optimization-project/blob/master/views/js/main.js).

- *Lines 424-445* The function changePizzaSizes has been changed to generate a size based on a percentage of the width of the parent div, removing the determine dx function and multiple DOM queries for the same element. This solution is based upon the solution provided in Udacity's Browser Rendering Optimization Lesson 5: [Styles and Layout: Stop Forced Synchronus Layouts](https://classroom.udacity.com/nanodegrees/nd001/parts/00113454012/modules/273584856175461/lessons/4147498575/concepts/41542085800923#). *This link may not be viewable if you are not currently enrolled!*
- *Lines 494-500* The variable docReq is created outside the for loop that moves the pizzas to minimize DOM queries.
- *Lines 519-521* Makes variable pizzaCount determined by the window height to prevent generating and animating images outside the viewable area.
