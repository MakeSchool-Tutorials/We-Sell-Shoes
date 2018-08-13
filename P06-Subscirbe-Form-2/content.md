---
title: "Subscribe-Form-2"
slug: subscribe-form-2
---
On landing pages it's important to repeat things several times, especially actions you want your users to take. This is why we will repeat the subscribe form a few more times throughout this process.

# Mark it up

Underneath our gallery, lets add the following:

```HTML
<div class="subscribe-2">
  <h1>"Nobody has better shoes than them!"</h1>
  <h3>- Turd Ferguson, Shoe Fanatic</h3>
  <div class="sub-fields">
    <input class="email-input" placeholder="Your e-mail"><button class="email-sub">Subscribe</button>
  </div>
</div>

```
Awesome! You'll notice that this looks exactly like our other subscribe form. The only thing that changed is that we appended a -2 to the subscribe class. This is so we can use a different background. Let's go ahead and do that now.

# Style it up

Underneath our old styles, let's add this:

```CSS
/****************
subscribe 2
****************/

.subscribe-2 {
  height: 50vh;
  width: 100%;
  background: linear-gradient(rgba(0,0,0,.6), rgba(0,0,0,.6)), url('https://images.pexels.com/photos/450059/pexels-photo-450059.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940');
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

Believe it or not, that's all we have to do.

This is the power of CSS! We can reuse old classes whenever we want.

let's take another look at what we've created.

![animated make cookies](images/cookies.gif "make cookies landing page")    

# Onward

Next thing up is some testimonials. This is going to be another interesting section.
