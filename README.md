## Website Performance Optimization portfolio project

### How to Run

- Go to https://ksarvas.github.io/WebsiteOptimization/ to view the current build's site
- Copy the URL above to https://developers.google.com/speed/pagespeed/insights/ to determine the pageSpeed score
- Click on "Cam's Pizzeria" to go to the pizza.html page
- Within pizza.html, open up dev tools to inspect the FPS while scrolling within a recorded Timeline
- Within pizza.html, open up dev tools to inspect the time to resize pizzas metric

### Optimizations Made: index.html

- Added Async attributes to each Script tag
- Resized and Compressed the profilepic and pizzeria thumbnail image (made a small version of pizzeria.jpg called pizzeria_small.jpg)
- Inlined all CSS for this page
- Added the media attribute to the css print link tag so that it was only called when media equaled print

### Optimizations Made: main.js

##### updatePositions Optimizations

- Created a global items variable outside of the updatePositions function which is assigned the value of document.getElementsByClassName('mover') right after the moving pizzas are created (see line 563)
- Stored the scrollTop value in a variable called scrollTop
- Created the phaseArray which stores the 5 values that Math.sin(scrollTop + i) creates
-Changed the for loop to only change the left position based on looped values in the phaseArray
- Added a requestAnimationFrame to the scroll event listener

##### DOMContentLoaded Optimizations

- Took the movingPizzas1 selector outside of the for loop and used getElementById instead
- Moved items definition here and changed selector to getElementsByClassName
- Created a resized version of pizza.png to the height and width specified in DOMContentLoaded so that the img didn't need to be resized each time

##### changePizzaSizes Optimizations

- Moved the dx and newwidth variables outside of the for loop
- Created a randomPizzaContainer variable that selected the randomPizzaContainer Class through getElementsByClassName
