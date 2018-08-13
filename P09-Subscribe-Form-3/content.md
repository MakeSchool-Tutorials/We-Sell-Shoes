---
title: "Subscribe-Form-3"
slug: subscribe-form-3
---
Let's add in our third subscribe section.

# Mark it up

Underneath our testimonials, lets add the following:

```HTML
<div class="subscribe subscribe-3">
  <h1>"I would kill for these shoes!"</h1>
  <h3>- Genghis Khan, Famous Barbarian</h3>
  <div class="sub-fields">
    <input class="email-input" placeholder="Your e-mail"><button class="email-sub">Subscribe</button>
  </div>
</div>
```
Now we can add in a new background.

# Style it up

Underneath our other styles, let's add this:

```CSS
/****************
subscribe 3
****************/

/****************
subscribe 3
****************/

.subscribe-3 {
  height: 50vh;
  width: 100%;
  background: linear-gradient(rgba(0,0,0,.6), rgba(0,0,0,.6)), url('https://images.pexels.com/photos/631986/pexels-photo-631986.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940');
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: white;
}

```
Great!

let's take another look at what we've created.

![animated make cookies](images/cookies.gif "make cookies landing page")    

# Onward

Next thing is the FAQ section. Lets get right to it!
