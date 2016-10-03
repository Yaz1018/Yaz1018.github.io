frontend-nanodegree-web-perf
==========================
## Website Performance Optimization portfolio project

A basic portfolio site who's sole purpose is to direct to the views/pizza.html.

## Hosted:
I used github.io to host and test everything.

## Setup - Installation
For the game to function correctly, you need to have a directory containing:
1. index.html
2. project-2048.html
3. project-mobile.html
4. project-webperf.html
5. 'css' folder
  style.css <!-- * This is actually not used due to inlining, but I left in for ease of reading -->
  * print.css
6. 'img' folder
  * 2048.png
  * cam_be_like.jpg
  * mobilewebdevs.jpg
  * profilepic.jpg
7. 'js' folder
  * perfmatters.js
8. 'views' folder
  * pizza.html
  * 'css' folder
    a. bootstrap-grid.css
    b. bootstrap-grid.min.css
    c. style.css
  * 'image' folder
    a. pizza.png
    b. pizza-sm.png
    c. pizzeria.jpg
  * 'js' folder
    a. main.js
    b. main.min.js
    c. main1.js <!-- * same as main.min except without the performance trackers -->
9.  README.md

If these items are not arranged correctly, or case is not followed, they will not be found.

### index.html:
Received a pagespeed score of 95/100 mobile & 97/100 desktop.
 * Used @media to call print.css only when needed
 * Minified and inlined the css since there wasn't much
 * Called my font/style as through js to remove render blocking
 * Minified and ascync'ed my performance trackers to remove blocking
 * Optimized my img folder through 3 filters

### pizza.html:
  * Had to change the viewport so i could make it work on mobile
  * Added backface-visibility:hidden; to .movers in style.css
  * Ran code through http://autoprefixer.github.io/
  * Minified and inlined ALL css, both style.css and bootstrap-grid.css
  * Optimized the images 3 (4 for the pizzeria.jpg) x through filters
  * main.js
    - wherever possible changed to getElementsByClassName 
    - resizePizzas() refactored loop to keep it simple
    - refactored pizzasDiv to moved the object outside the loop as to not call document.getElementById 100x!
    - refactored updatePositions() to only call sin once
    - used a 2nd loop and style.transform to increase efficiency of the .movers
    - addEventListener('scroll' now calls requestAnimationFrame
    - shrunk images in px size to now resize them in browser (~22x)
    - instead of a set number of pizzas, I changed it to be depenent of the viewport to improve mobile performance

## Known bugs
The .movers are not mobile optimized... pizzas are cut off and not many are seen. 

## MIT License

Copyright (c) [2016] [Garon Davis]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.