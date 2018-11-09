---
title: "Making A Plan!"
slug: Making-A-Plan
---

Become a master of the world by creating a landing page for
the worlds best shoe store, your shoe store.

# Making A plan
All websites need a home page, and shoe selling is no exception. We are going to create a homepage from scratch, while practicing modern design tools, and best practices, all without aid of any libraries or frameworks.

To start we will plan out the different sections and features we would like to have on our website.

- We need a Navigation bar
- We need a Hero image section along with a call to action button   
- We need a space to showcase current clients
- We need a space to collect emails
- We need the shop itself
- We need a testimonial section
- We need an FAQ
- We need a footer

Because this is going to be mostly just a static webpage, we will have only few user stories. Let define them:

- As a user, if I wait 60 second a popup will appear, I can exit this popup by clicking the X.
- As a user, I can view different testimonials by clicking on the navigation buttons.
- As a user, I can open and close the tabs on the FAQ section.
- As a user, if I hover over certain thing, small animations will occur.

With all this in mind we are ready to start!  

# Getting started

The first thing that we need to do is create a directory for our files.

From your Terminal, navigate to where you'd like to create a new folder and execute the following command:

```
mkdir we-sell-shoes
```

Navigate into the directory you just created with the command:

```
cd we-sell-shoes
```

# Create your first file

Next, you'll need to create a new file called ```index.html```. This is where the page will live.

You can do this by executing the following commands in your terminal:
```
touch index.html
```

Now all that's left to do is open ```index.html``` inside your favorite text editor. If you use Atom, you can use the following command from your terminal:

```
atom .
```

Now that we've created our files, we're ready to put our shoes on the production line.

# HTML Template

The first thing we're going to do is add in a basic HTML Template.

Inside of index.html, please write the following:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>We Sell Shoes</title>
  </head>
  <body>

  </body>
</html>
```
Once we have our basic **HTML5 boilerplate** we're ready to create a few more files that will help us out.

# Adding An External Stylesheet and Javascript File

In order to avoid messy code, we'll use two extra files to organize our CSS and Javascript.

Inside of the terminal we will create two new files with the following line of code:

```
touch index.js && touch styles.css
```

Adding ```&&``` after any command in the terminal lets you run as many commands as you want in order.

Now that we've got our separate files, we will need to import them into our HTML.

# Importing Our Files!

Inside of index.html, let's add the following lines of code:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>We Sell Shoes</title>

    <!-- Link in our stylesheet -->
    <link rel="stylesheet" href="./styles.css">
    <!-- Make sure this is inside of our <head> -->

  </head>
  <body>

    <!-- Link in our Javascript file -->
    <script src="index.js"></script>
    <!-- Make sure this is below our closing <body> -->

  </body>
</html>

```   

You'll notice that we organize our Stylesheets in our head, and our javascript files right before our closing body tag.

We put our stylesheets in the head because we want the browser to load our styles before it loads the rest of the page. Likewise we put our Javascript at the closing body tag because we want the browser to load our scripts after everything else loads.    

# Onward

We now have a basic template ready to be used.

And just like that we're all set and ready for some shoe customers!
