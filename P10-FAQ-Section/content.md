---
title: "FAQ Section"
slug: FAQ-Section
---

Most online stores seem to have a section for frequently asked questions. We are going to have one as well.

In this section we will create an Accordian style FAQ panel from scratch.

# Mark our territory
Let's begin by getting the markup out of the way.

Put this code below the third subscribe form:

```HTML
<div class="faq">
  <h2>Frequently Asked Questions</h2>
  <div class="faq-container">
      <button class="accordion">How do I tie my shoes?</button>
      <div class="faqpanel">
        <p>Lace them together.</p>
      </div>

    <button class="accordion">I lost one of my shoes, can I purchase just one?</button>
    <div class="faqpanel">
      <p>No.</p>
    </div>

    <button class="accordion">You don't carry the shoes in my size.</button>
    <div class="faqpanel">
      <p>Tough luck</p>
    </div>
  </div>
</div>

```
Awesome work. Feel free to change/add questions as you wish.

It's time to add some styles to create the accordion.

# Style time

Make sure this is at the bottom of your stylesheet.

```CSS
/**********
faqpanel
************/


.faq {
  width: 100%;
  background: white;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-bottom: 2rem;
}

.faq h2 {
  text-align: center;
}

.faq-container {
  width: 60%;
}


.accordion {
    background-color: #eee;
    color: #444;
    cursor: pointer;
    padding: 18px;
    width: 100%;
    text-align: left;
    border: none;
    outline: none;
    transition: 0.4s;
    font-weight: 600;
}

/* Add a background color to the button if it is clicked on (add the .active class with JS), and when you move the mouse over it (hover) */
.active, .accordion:hover {
    background-color: #ccc;
}

/* Style the accordion panel. Note: hidden by default */
.faqpanel {
    padding: 0 18px;
    background-color: white;
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.2s ease-out;
}

.accordion:after {
    content: '\02795'; /* Unicode character for "plus" sign (+) */
    font-size: 13px;
    color: #777;
    float: right;
    margin-left: 5px;
}

.active:after {
    content: "\2796"; /* Unicode character for "minus" sign (-) */
}

```
Awesome. Now it looks like a pretty good accordion.

But we can't interact with it yet. Let's fix that.

# Making the FAQ Section interactive

We need to use some client side Javascript in order to get our FAQ Section to work properly.

Let's add this to the bottom of our code:

```js
/////////////FAQ accordion section///////////////


//delcare default vars
const acc = document.getElementsByClassName("accordion");

//loop through all accordion buttons
for (let i = 0; i < acc.length; i++) {

  //trigger an event after click
  acc[i].addEventListener("click", function() {

    //add in the active class

    //select sibling element

    //if sibling is open, close it, if closed, open it
    if (panel.style.maxHeight){
      //panel is open

    } else {
      //panel is closed

    }
  });
}


```

Great. We're almost done. We still have some blanks to fill in.

```js
//add in the active class
this.classList.toggle("active");
```

We defined our active class in our stylesheet.

```js
//select sibling element
let panel = this.nextElementSibling;
```
The panel will be the div below that contains our answer.

```js
//if sibling is open, close it, if closed, open it
if (panel.style.maxHeight){
  //panel is open open
  panel.style.maxHeight = null;

} else {
  //panel is closed
  panel.style.maxHeight = panel.scrollHeight + "px";
}

```
Great! That's how we make a nice FAQ Accordion in vanilla JS.

Let's take a look at what the finished FAQ should look like:

![faq](images/faq.png "faq")  

# Onward
The next section of our website is going to be the footer!
