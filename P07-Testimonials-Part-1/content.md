---
title: "Testimonials Part 1"
slug: testimonials-1
---

Testimonials are super important! In the digital age, nobody wants to purchase something unless the reviews are good.

We can establish some slight rapport with our customers by adding in some testimonials.

# Marking it up!

Let's do some mark-up shall we?

```html
<div class="testimonials">
  <h1 class="testimonial-title">Testimonials</h1>
    <div class="tests first">
    <div class="testimonial testimonial-1">
      <img src="http://infasme.com/wp-content/uploads/2017/05/Faces-400x400px-1_1_07-scalia-testimonial.jpg" class="testimonial-image" />
      <div class="testimonial-quote">This product was amazing.<p> - John Setzen</p></div>
    </div>

    <div class="testimonial testimonial-2">
      <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSjvtBy5YBKiYcLTPgiQXdPNUK0c4cma-EoXPPuay1ba4-7kJLj" class="testimonial-image" />
      <div class="testimonial-quote">This product was great. <p>- John Setzen's Twin Brother</p></div>
    </div>

    <div class="testimonial testimonial-3">
      <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQbJAJEmKnMZWlu3aXB-5J9kqlppVCOH-xlFYQKuNWQY1BwpMsD" class="testimonial-image" />
      <div class="testimonial-quote">This product was pretty good. <p>- Professional John Setzen Look Alike</p></div>
    </div>
  </div>

  <div class="dots">
    <div id="prev" class="dot"></div>  <div id="next" class="dot"></div>  <div id="next-next" class="dot"></div>
  </div>

</div>

```  
We have a lot of markup for these testimonials because we want them to be interactive. The dots class you see will be used to navigate through our testimonials.

Let's get some styles going now.

# Making our testimonials stylish

This is going to be a little in depth, so bare with me.

```CSS
/**********
testimonials
**********/

.testimonials {
  margin-top: -2rem;
  height: 80vh;
  width: 100%;
  background: #ecf0f1;
}

.testimonial-title {
  padding-top: 1rem;
  text-align: center;
}

.tests {
  position: absolute;
  width: 300%;
  display: flex;
  transition: all 400ms;
}

.tests.first {
  right: -200%;
}

.tests.second {
  right: -100%;
}

.tests.third {
  right: 0%;
}


.testimonial {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
}

.test1 {
  position: absolute;
  left: 0;
}

.test2 {
  position: absolute;
  left: 33%;
}

.test3 {
  position: absolute;
  left: 66%;
}


.testimonial-image {
  border: solid 8px white;
  border-radius: 50%;
  height: 272px;
  width: 272px;
}

.testimonial-quote {
  margin-top: 1rem;
  border: solid 15px white;
  border-radius: 2px;
  background: white;
}

.testimonial-quote p {
  text-align: center;
  margin-bottom: 0;
}

.dots {
  align-self: baseline;
  margin-top: 28rem;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  width: 100%;
}

.dot {
  border: solid 1px black;
  border-radius: 100%;
  height: 8px; width: 8px;
  margin-right: 1rem;
  transition: all 200ms;
}

.dot:hover {
  background: black;
}

```  
What's going on here?

We gave our .tests class a width of 300% and our indivdual testimonials a width of 100%. This is because we want each one to take up 100% of the page.

Since we don't want them all to appear at once, we give them a position: absolute, and set their styles so they appear off the page.

Theres a problem though...

![oh no](images/ohno.gif "Oh no")  

Oh No! We can drift off the side of the page. Let's quickly fix that!

```CSS
this is the top of your CSS File
body {
  margin: 0;
  /*add this line below*/
  overflow-x: hidden;
}

```
That should do it!

But now a new problem presents itself, now that we can't scroll to them, there's no way to see them.

This is where javascript comes into play.

We will add our interactive javascript in part two.

# Onward   
In the next section we will add functional javascript to make our testimonials work.
