## Website Performance Optimization portfolio project

This optimization project was completed as part of the Udacity's Frontend Web-Developer Nanodegree program. The basic instructions were as follows:


"Your challenge, if you wish to accept it (and we sure hope you will), is to optimize this online portfolio for speed! In particular, optimize the critical rendering path and make this page render as quickly as possible by applying the techniques you've picked up in the [Critical Rendering Path course](https://www.udacity.com/course/ud884)."


Optimizations include:
1. Images have been scaled and compressed using a combination of Gimp, tinypng.com and tingyjpg.com. Some images have been converted to a more appropriate format.
2. Some CSS files, such as print.css, were optimized by adding a media query so
that they only load when needed, thus preventing unnecessary render blocking.
3. Styling needed for above-the-fold content is placed as inline CSS in the 
HTML files. External CSS files are generated dynamically after the page loads using a JavaScrip function, thus preventing render blocking.
4. Any scripts that are not immediately required to load the page are designated 
asynchronous with the "async" HTML attribute. This allows the parser
to continue constructing the DOM and only execute the script when it's ready.
5. Google Open Sans font was replaced with web-safe Helvetica font. 
6. The JavaScript for Cam's Pizzeria page has been optimized by taking expensive
calculations out of the loops, especially in the updatePositions() function. This
prevents unnecessary recalculations/layouts during scrolling. Unnecessary and expensive repaints of the background are avoided by adding "backface-visibility: hidden" to the CSS styling.
7. Large CSS files and JavaScript files have been minimized -- removing "white space" and comments reduces file size, which means less to load.

To view the web-page locally on your computer, follow these steps:
1. Download the zip file and extract its contents.
2. Open the index.html file in a browser.

To test the peformance of the website:
1. Open the following link in your browser: http://gremlin12.github.io/frontend-nanodegree-mobile-portfolio/
2. Copy the URL address.
3. In a new tab, go to PageSpeed Insights at https://developers.google.com/speed/pagespeed/insights/
4. Paste the web page URL into the input form on Pagespeed Insights and click the "analyze" button.
5. Repeat steps 2-4 for all the links found on http://gremlin12.github.io/frontend-nanodegree-mobile-portfolio/

Sources:
"Render Blocking CSS" [https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css] for help with media types and media queries
"Adding Interactivity with Javascript" [https://developers.google.com/web/fundamentals/performance/critical-rendering-path/adding-interactivity-with-javascript] provided the JavaScript code to generate CSS files dynamically.
"Image Optimization" [https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization] for help with formatting and compressing images.
Ben Frain's blog-post "Improving the CSS Performance of Fixed Position Elements" [http://benfrain.com/improving-css-performance-fixed-position-elements/] provided the "backface-visibility: hidden" trick to prevent unnecessary repainting of background when scrolling.
"Pagespeed" by feedthebot [http://www.feedthebot.com/pagespeed/] provided a lot of useful general information about website optimization.
Alex Danilo's blog-post "User Timing API" [http://www.html5rocks.com/en/tutorials/webperformance/usertiming/] helped in understanding how to measure performance with the User Timing API.
Paul Irish's post "Why Moving Elements With Translate() Is Better Than Pos:abs Top/left" [http://www.paulirish.com/2012/why-moving-elements-with-translate-is-better-than-posabs-topleft/] -- title is self-explanatory.
Richard Thompson's TechPortal article "Improve Rendering Performance with Chrome Dev Tools" [http://techportal.inviqa.com/2014/04/09/improve-rendering-performance-with-chrome-dev-tools/] was especially helpful in understanding how to measure FPS.