---
title: "Testimonials Part 2"
slug: testimonials-2
---

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
These are all going to use const, because they will not change.

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

To learn more about the setInterval method, check out this resource: https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval

![Testimonial Cycle](images/cycle.gif "Testimonial Cycle")

# Event Listeners

By default, we show the testimonial associated with the .prev class. We want to create an event listener that let's us move to the next one. Let's do it step by step.

Put this code at the bottom.

```js
//Create a reusable function for clicking on the dots.
function dotClick(oldClassOne, oldClassTwo, newClass) {
  if (tests.classList.contains(oldClassOne)) {
    tests.classList.remove(oldClassOne);
  }

  if (tests.classList.contains(oldClassTwo)) {
    tests.classList.remove(oldClassTwo)
  }

  window.clearInterval(nextNextInt);
  window.clearInterval(nextint);
  window.clearInterval(prevint);
  tests.classList.add(newClass);
}


```
Because we can click any dot no matter what position we're in, we have to remove the other classes because we add the one that brings us where we need to go.

We will go in depth on eventListeners and DOM Manipulation in the Make Cookies tutorial.

Now we can add the others below:

```js
nextNext.addEventListener("click", function() {

  dotClick('second', 'first', 'third');

})



next.addEventListener("click", function() {

  dotClick('first', 'third', 'second');

})

prev.addEventListener("click", function() {

  dotClick('second', 'third', 'first');

})

////////////////// end of testimonial section
```

we call the dotClick function we defined above, and pass in the class names we need to get rid of in the first two parameters, and the class name we want to add in the third.

Nice, we now have an interactive testimonial section.

![testimonial cycle 2](images/cycle2.gif "Testimonial cycle 2")

# Onward

The next session will give us a bit of a break, as we will just be adding in a third subscribe section.
