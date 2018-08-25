---
layout: step
number: 4
title: Functions
permalink: step4/
requirements:
  - variables
  - values, expressions, Operators
  - conditionals

# keywords:
#  - term: package.json
#    define: A `package.json` is the file used to store information about a Node.js project, such as its name and its dependencies. Read more [here](https://docs.npmjs.com/files/package.json).

---

Functions are a way of taking the big todo list of our program and breaking it up into a series of smaller ones.  It's a little bit like writing lots of tiny program inside of your program (we heard you like programs so we put programs in your program).

We've been using functions so far to assign behaviour to events, specifically the `onclick` events of our buttons.

However breaking your code up into functions is helpful for a few other reasons.

1. Small programs are easier to write than big ones, and functions let us write our big programs as though they were a bunch of little ones instead.
2. It can make our programs easier to read and understand.
3. It can also save you time by letting you reuse your functions in multiple places.

So lets explore functions by creating a new app.  Create a new HTML file with the following:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Learning JS workshop</title>
  </head>
  <body>
    <div style="padding:10px; margin: 15px; border:1px solid grey; background-color:#ffffff">
      Background: <input id="bgColorInput" name="background" type="color" value="#ffffff"  />
      Row1: <input id="row1ColorInput" name="row1" type="color" value="#ffffff"  />
      Row2: <input id="row2ColorInput" name="row2" type="color" value="#ffffff"  />
    </div>
    <div id="message"></div>
    <div id="row1" style="width:100%;height:100px"></div>
    <div id="row2" style="width:100%;height:100px"></div>
  </body>

  <script>

    function getMessage(color, elementId){
      var elementName = '';
      if(elementId === undefined){
        elementName = 'the background'
      } else {
        elementName = "<div> " + elementId;
      }
      return elementName + " was updated to be colour "+color;
    }

    function setColor(color, elementId){
      if(elementId === undefined){
        document.bgColor = color;
      } else {
        document.getElementById(elementId).style.backgroundColor = color;
      }
      document.getElementById('message').innerText = getMessage(elementId, color);
    }

    function colorChange(event){
      if(event.target.name === 'background'){
        setColor(event.target.value);
      } else {
        setColor(event.target.value, event.target.name);
      }
    }

    document.getElementById('bgColorInput').onchange = colorChange;
    document.getElementById('row1ColorInput').onchange = colorChange;
    document.getElementById('row2ColorInput').onchange = colorChange;
  </script>

</html>
```

Check it out in your browser.  

[INSERT SCREENSHOT]

You should see three colour well elements that when clicked open colour pickers. This is done by using `<input>` elements with `type` set to `color`.
Selecting a colour will update the background colour of either the page or one of two `<div>`s.

So like the previous pages we've made, we've got some elements, and some functions that we assign to events on those elements.

But we've done a few things differently this time:

1. We are using the `onchange` event instead of `onclick`.
2. We assigned the same function to an event on multiple different elements.
3. Our function assigned to `onchange` has what we call a **parameter**.
4. We have written some other functions which we are using directly instead of assigning it to an event.

### The `onchange` event

Some elements, like `<input>`, can issue an `onchange` event.
They do this when the value that they are responsible for changes.
This means the event doesn't fire when the element is clicked on, only when you actually pick a different colour in the colour picker.

### Function parameters and arguments

Functions that are assigned to events like `onclick` and `onchange` get run (**invoked**) by the browser when those events happen.
You don't get to see the code that does that, so something that isn't obvious is that the browser passes some extra stuff along when that happens.  This passing along of data is called **passing arguments**.  To handle those arguments you need to **declare parameters** in your function.

Lets look at our function `colorChange`:

```javascript
function colorChange(event){
  if(event.target.name === 'background'){
    setColor(event.target.value);
  } else {
    setColor(event.target.value, event.target.name);
  }
}
```

This code is what we call the **function declaration** of `colorChange`.

Function declarations have four distinct parts.

1. The `function` keyword.  This tells Javascript that we are declaring a function.
2. The name of the function, in this case `colorChange`.
3. The parameter list in parentheses, `()`.  If you declare multiple parameters they must be separated by commas.  If you don't declare any parameters, you just have empty parentheses.
4. The body of the function in braces, `{}`.  This is what gets run when the function is invoked.

We've seen all of that before in previous examples except the parameter list.

What declaring parameters does is create some variables each time the function is invoked.  The values of any arguments is assigned to those variables.  

Ok so how did we use that in `colorChange`?

Well when a function is


### Invoking functions and passing arguments


### Function return values
