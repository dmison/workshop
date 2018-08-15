---
layout: step
number: 4
title: Objects
permalink: step4/

# keywords:
#  - term: package.json
#    define: A `package.json` is the file used to store information about a Node.js project, such as its name and its dependencies. Read more [here](https://docs.npmjs.com/files/package.json).

---

One of the types we mentioned earlier was **objects**.

Objects are like values that contain multiple variables.

Objects give us a way of collecting related variables together as a single value.

```javascript
var cat = {
  name: 'Garfield',
  weight: 8.2,
  colour: 'orange',
  likes: 'lasagna',
  hates: 'Mondays'
};
```

This is much more convenient that having a bunch of different variables, eg. `catName`, `catWeight`, `catColour`, etc.

The values contained in an object are often referred to as the object's **properties**.

You can access the properties of an object in two ways: **dot syntax** and **by key**.

## Dot Syntax

```javascript
cat.colour
```

## Key Syntax.
```javascript
cat["colour"]
```

Note that the key here is a string, so we can use a variable or expression here as well.

Object properties can also be functions.
We'll talk more about how that works a little further down.

You've already been using objects this whole time by the way.

Lets look at the `doStuff` function we've been using for displaying our message so far:

```javascript
function sayStuff(){
  document.getElementById('displayBox').innerText = message;
}
```

There's actually multiple steps going on in that one line.
Let's re-write it as the multiple steps so we can see what's really happening:

```javascript
function sayStuff(){
  var displayBox = document.getElementById('displayBox');
  displayBox.innerText = message;
}
```

`document` is an object.  

It gets automatically created when our page loads and it contains everything about the current page and what is happening in it.  
It's is what we use to do anything to the page with Javascript.

`document` has *lots* of properties.

[document reference](https://developer.mozilla.org/en-US/docs/Web/API/Document)

## Functions as values

So we said earlier that objects can have functions as properties. How can that be if objects contain named values?  

Well in Javascript, functions *are* values.  The definition of the function itself is a value.  This means that the function itself can be assigned to a variable.  

So you can do this for example:

```javascript
function meow(){
  console.log('meow!');
}

cat.speak = meow;

cat.speak();
```



But it also lets you pass a function as a parameter.  We'll touch on that briefly when we talk about arrays.

So now the assignment of functions to events like `onclick` should start to make a bit more sense.  Lets look at that again quickly.

```javascript
function handleSay(){
  var name = document.getElementById('nameInput').value;
  var message = makeMessage(name, status);
  document.getElementById('displayBox').innerText = message;
}

document.getElementById('sayButton').onclick = handleSay;
```

So what is `onclick` exactly?  `onclick` is a property of a HTML element which is a function.  That function is invoked when the button is clicked on.  By default `onclick` does nothing.

We created a function called `handleSay`.  Then we use `document.getElementById` to get a reference to the element with the id of `sayButton` (which happens to be a button).  We then assign the function `handleSay` to the button's `onclick` property.
