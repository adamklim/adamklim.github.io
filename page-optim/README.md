# Introduction

This website is a part of performance optimization project for Udacity FEND course.
For the project, a website was provided by Udacity, and was subsequently edited to improve performance in the following areas:
1. Google PageSpeed Insights should indicate over 90/100 for mobile and desktop view for the main page.
2. Animations on page /views/pizza.html should run at 60fps or more.
3. Pizzas resize on page /views/pizza.html should be at 5ms or less.

**To view the website, visit [https://adamklim.github.io](https://adamklim.github.io)**


# Changes made:

## PageSpeed optimizations:

* optimized image size and compression
* minified and inlined style.css
* print.css tag media="print"
* Google Analytics moved to bottom of body
* asynchronous load of Google Analytics
* WebFont loader at bottom of the body
* minified css and js files
* HTML minified



## Pizzas animation optimizations:

Major bottleneck in function updatePositions - multiple layout recalculations were triggered

### solution:
* Major bottleneck in function updatePositions - multiple layout recalculations triggered
	* Variable phase had only 5 values, so it's taken out of loop that calculate pizzas position - fixes layout recalculation.
  * phase values are now stored in array.
  * DOM method changed from .querySelectorAll to .getElementsByClassName
* Number of objects to be animated changed from fixed (200) to number relative to viewport size.


## Pizzas resize optimization:

Optimizations to  ChangePizzaSizes were needed - multiple layout recalculations triggered.

* .querySelectAll methods replaced with .getElementsByClassName
* .querySelect methods replaced with .getElementById
* optimization of ChangePizzaSizes function: variables dx and newwidth removed from for-loop to avoid layout recalculations, new variable randomPizza included.


