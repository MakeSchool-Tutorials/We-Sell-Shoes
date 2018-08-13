So we left off with having the styles complete, now we need to add some functionality with javascript.

# Plan it out
Let's first plan out what we'd like to implement.

- The testimonials should cycle through on their own
- As a user, I should be able to hit one of the circles to show a different testimonial

We can infer from these what we may need to implement:

- We will need click event listeners
- we will need some sort of looped action on a timer

With these in mind, let's begin!

# Define our Variables

First we will define our variables at the top of our ```scripts.js``` file.

```js
/*************
testimonial section
**************/

//three dots
const nextNext = document.getElementById('next-next')
const next = document.getElementById('next');
const prev = document.getElementById('prev');

//individual testimonials
const testi1 = document.querySelector('.testi1');
const testi2 = document.querySelector('.testi2');
const testi3 = document.querySelector('.testi3')

//testimonial parent container
const tests = document.querySelector('.tests');

```  
These are all going to use const,because they will not change.

# Interval Timers
We want the testimonials to automatically cycle through. Let's add these lines of code below our variables.

```js
let nextNextInt = window.setInterval(function() {
  //check for and remove second class
  if (tests.classList.contains('second')) {
    tests.classList.remove('second');

    //add the class which shows the third testimonial
    tests.classList.add('third');
  }

}, 4000)


let nextint = window.setInterval(function() {
  //check for and remove first class
  if (tests.classList.contains('first')) {
    tests.classList.remove('first');

    //add the class that shows the second testimonial
    tests.classList.add('second');
  }

}, 8000)

let prevint = window.setInterval(function() {
  //check for and remove third class
  if (tests.classList.contains('third')) {
    tests.classList.remove('third');

    //add the class that has the first testimonial
    tests.classList.add('first');
  }
}, 16000)
```

The way this works, is the next actions won't occur unless the testimonial parent container already contains the class that shows the testimonial closest on the right.

This should cycle us through the all the testimonials on repeat.

![Testimonial Cycle](images/cycle.gif "Testimonial Cycle")

# Event Listeners

By default, we show the testimonial associated with the .prev class. We want to create an event listener that let's us move to the next one. Let's do it step by step.


```js
//middle dot click
next.addEventListener("click", function() {

  //check to see what class the container has, and remove old classes
  if (tests.classList.contains('first')) {
    tests.classList.remove('first');
  }

  if (tests.classList.contains('third')) {
    tests.classList.remove('third');
  }

  //clear the timing interval
  window.clearInterval(nextNextInt);
  window.clearInterval(nextint);
  window.clearInterval(prevint);

  //add the second class to the container to cycle it through
  tests.classList.add('second');

})


```
Because we can click any dot no matter what position we're in, we have to remove the other classes because we add the one that brings us where we need to go. 
