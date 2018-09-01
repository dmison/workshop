---
layout: step
number: 10
title: External Scripts
permalink: step10/
---

We’ve been using the `<script>` tag with our JavaScript inside of it in our webpages.

This is fine for the simple pages we have been building, but it can quickly get impractical if you have a lot of JavaScript.  Also what if you want the same JavaScript to appear in multiple pages?

We can use `<script>` to reference JavaScript in a different file.  This is very similar to how you can put CSS in separate files to your HTML.

To do this:

1. Put your JavaScript in it’s own file.  Usually we use the `.js` extension and name the file appropriately for what it is.
2. Use the `<script>` tag with the src attribute set to your file

Let’s update the very first example from step 1 to use this:

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
  <script src=“myscript.js”> </script>
</html>
```

Now put all the JavaScript into `myscript.js`:
```javascript
function doStuff(){
  document.getElementById('displayBox').innerText = 'You clicked the button!';
}
document.getElementById('actionButton').onclick = doStuff;
```

The `src` attribute of `<script>` is very similar to the `src` attribute of `<img>`.

Have a try updating some of the previous examples you have done.
