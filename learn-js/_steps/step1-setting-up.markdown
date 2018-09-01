---
layout: step
number: 1
title: Setting Up
permalink: step1/
---

A lot of beginning workshops for JavaScript start you with the very basics and only start doing the fun stuff (like using the DOM) at the end.

That's kind of boring, so we want to jump right in with the fun stuff.

So let's get started with a simple page that has a button and a box.

Then we are going to write some code that will make changes to the box when you click the button.

I'll describe what all of this does, and then in the following steps we will expand on those explanations and make it do more stuff.

Ready?  Let's go!

Create a new HTML file, call it whatever you want just so long as it has `.html` at the end, then add the following to it:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Learning JS workshop</title>
  </head>
  <body>
    <button id="actionButton">Click me</button>
    <pre id="displayBox"></pre>
  </body>
  <script>
    function doStuff(){
      document.getElementById('displayBox').innerText = 'You clicked the button!';
    }
    document.getElementById('actionButton').onclick = doStuff;
  </script>

</html>
```

Save it and open that file in your browser.

You should see a button.

Now click on the button and you will see the text 'You clicked the button!' added to the page.

![An animated GIF of Anne Hathaway making a mind blown gesture](../assets/anne-hathaway-mind-blow.gif "Mind = Blown")

So what just happened here?

When the page loads in the browser, the browser reads the HTML file, and draws the HTML elements as it finds them in the file - until it hits the `<script>` tag.  

When it hits the `<script>` tag, the browser pauses drawing the page and runs the instructions in the `<script>` tag.
Once it finishes that it continues drawing whatever page elements it finds after `</script>`.

That's the first way a browser runs JavaScript code: when it finds a `<script>` tag when loading the page.

So what happens in our `<script>` tag?

```javascript
function doStuff(){
  document.getElementById('displayBox').innerText = 'You clicked the button!';
}
document.getElementById('actionButton').onclick = doStuff;
```

The code in our tag does two things.

First, our code creates a function which we named `doStuff`.
A function is a way of providing a chunk of code to run later.

When the `doStuff` function runs, it will find the element in the document (the page) with the ID of `displayBox` and set the text in that element to `You clicked the button!`.
`document` and `getElementById` are parts of the DOM API.

Next, our code finds the element with the element with the ID of `actionButton` and tells the browser that when that element gets clicked on, the browser should run the function `doStuff`.

So then when you click on the button, the text changes on the page.  

This is the second time that JavaScript code runs: when something that happens on the page has a JavaScript function attached to it. 
We call those things that happen `events`.

Running code in response to events is called *event-driven programming*, and that's what most JavaScript programming is.

Almost everything that happens in the browser triggers an event. 
Think of an event as an announcement from JavaScript that a specific thing happened. 

When the page loads, when you scroll, when you click on something, all these things and many more cause the browser to create events.

When we write JavaScript, we tell the browser what instructions (functions) to run when different events happen.

So now we have something to work with let's dig into the basics of JavaScript.
