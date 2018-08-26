---
layout: step
number: 1
title: Setting Up
permalink: step1/

# keywords:
#  - term: package.json
#    define: A `package.json` is the file used to store information about a Node.js project, such as its name and its dependencies. Read more [here](https://docs.npmjs.com/files/package.json).

---

A lot of beginning workshops for JavaScript start you with the very basics and only start doing the fun stuff (like using the DOM) at the end.

That's kind of boring, so we want to jump right in with the fun stuff.

So what we are going to do is create a simple page that has a button and a box.

Then we are going to write some code that will make changes to the box when you click the button.

I'll describe what all of this does, and then in the following steps we will expand on those explanations and make it do more stuff.

Ready?  Let's go!

Create a new HTML file, call it whatever you want just so long as it has `.html` at the end, then add the following HTML & Javascript to it.

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

[INSERT BRAIN EXPLODING GIF]

So what just happened here?

When the page loads in the browser, the browser reads the HTML file, and draws the HTML elements as it finds them in the file - until it hits the `<script>` tag.  

When it hits the `<script>` tag, the browser pauses drawing the page and runs the instructions in the `<script>` tag.  Once it finishes that it continues drawing whatever page elements it finds after `</script>`.

That's the first way a browser runs JavaScript code: when it finds a `<script>` tag when loading the page.

So what happens in our `<script>` tag?

```javascript
  function doStuff(){
    document.getElementById('displayBox').innerText = 'You clicked the button!';
  }
  document.getElementById('actionButton').onclick = doStuff;
```

The code in our tag does two things.  

First, our code creates a function which we named `doStuff`. A function is a way of providing a chunk of code to run later.

When the `doStuff` function runs, it will find the element in the document (the page) with the ID of `displayBox` and set the text in that element to `You clicked the button!`.  `document` and `getElementById` are parts of the DOM API.

Next, our code finds the element with the element with the ID of `actionButton` and tells the browser that when that element gets clicked on, the browser should run the function `doStuff`.

So then when you click on the button, the text changes on the page.  

This is the second time that Javascript code runs: when something that happens on the page has a Javascript function attached to it. We call those things that happen `events`.

Running code in response to events is called *event-driven programming*, and that's what most JavaScript programming is.

Almost everything that happens in the browser triggers an event. Think of an event as an announcement from Javascript that a specific thing happened. When the page loads, when you scroll, when you click on something, all these things and many more cause the browser to create events.

When we write Javascript, we tell the browser what instructions (functions) to run when different events happen.

So now we have something to work with let's dig into the basics of Javascript.

<!-- ## Script placement

You can actually put script tags anywhere in a page.  And you can use more than one.

Does it matter where the `<script>` tags go?

Remember how I said that the browser pauses updating page elements when it encounters a `<script>`?

In our page we have the `<script>` after `<body>`.  What do you think will happen if you were to put it before `<body>`?

Try it.  

The page will load but the button does nothing?  Why?

If you open up your browser developer tools and go to the console tab you will see an error something like this:

```
TypeError: document.getElementById(...) is null
```

This error occurs when the page loads.  Refresh the page to see.

This line is the one that tried to assign our `doStuff` function to the `click` event of the `actionButton` button.  But because the `script` tag was before the button in the page, we browser doesn't know about the button yet and so it can't find it.

The earlier line in the `doStuff` function that looks up `displayBox` doesn't produce an error because that line hasn't actually run yet. All we are doing there is creating the function, creating code that will run later. But that code will never run because although the function is created ok, it the line that assigned it to the click event didn't run successfully. -->
