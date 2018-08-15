---
layout: step
number: 4
title: Functions
permalink: step4/

# keywords:
#  - term: package.json
#    define: A `package.json` is the file used to store information about a Node.js project, such as its name and its dependencies. Read more [here](https://docs.npmjs.com/files/package.json).

---

Functions are a way of taking the big todo list of our program and breaking it up into a series of smaller ones.  It's a little bit like writing lots of tiny program inside of your program (we heard you like programs so we put a program in your program).

We do this for a couple of reasons.

1. Smaller programs are much easier to write.
2. It can make our programs easier to understand.
3. It can also save you time by letting you reuse your functions in multiple places.

It's the mechanism that JS uses for assigning behaviour to events.
So we *have* to use them for that. ;-)

We've already written a couple of very simple functions: `handleArrive`, `handleLeave`, and `sayStuff`, and we've made use of one that the browser provided: `getElementById`.

However we've only used the functions that we've created to assign behaviour to the `onclick` events of our buttons, and we've avoided a couple of very important features of functions, **parameters** and **return values**.

So let's rewrite our program a bit to take advantage of these.

---

First we'll replace

```Javascript
var status = 'unknown';
```

```Javascript
function makeMessage(name, status){
  var message = "I don't know here you are!";

  if(status === 'arrive'){
    if(name===''){
      message = 'Welcome stranger!';
    }else {
      message = 'Welcome '+name+'!';
    }
  }

  if(status === 'leave'){
      if(name === ''){
        message = 'Farewell stranger!';
      }
      else {
        message = 'Farewell '+name+'!';
      }
  }
  return message;
}
```

```Javascript
function handleArrive(){
  status = 'arrive';
}

function handleLeave(){
  status = 'leave';
}
```

```Javascript
function handleSay(){
  var name = document.getElementById('nameInput').value;
  var message = makeMessage(name, status);
  document.getElementById('displayBox').innerText = message;
}
```

```Javascript
document.getElementById('sayButton').onclick = handleSay;
document.getElementById('arriveButton').onclick = handleArrive;
document.getElementById('leaveButton').onclick = handleLeave;
```

## Parameters & Arguments.

Functions can be sent explicit values to use when invoked.  We call this **passing arguments**.

This is like having special variables in your function which are initialised with values when the function is invoked.

To pass arguments, simply list the values (or variables) you want to send with commands between them in the parentheses after the when you invoke a function.

To make use of the values passed in, you must define **parameters** when declaring the function.  To define parameters, you list the names with commas between them that you want them to have in the parentheses after the function name.

Example: declaring a function called getFullName that takes two arguments.

```javascript
function getFullName(firstname, lastname){
    var fullname = firstname + ' ' + lastname;
}
```

Now when you invoke the function you can specify values for those parameters.  We call that **passing arguments**.

```Javascript
getFullName('Jessica', 'Smith');
```

**Parameters** and **arguments** are two terms that tend to get used interchangeably.  Everybody mixes them up. :-)

## Returning values

A function can return a value.  

To return a value you use the `return` keyword followed by the value or variable to return.  

When the `return` keyword is encountered in a function, it immediately stops running and flow returns to the caller.

When a function returns a value, you can use the invocation of that function any place where a value is expected.  A little bit like variables.

So let's extend `getFullName` so it **returns** `fullname`.

```Javascript
function getFullName(firstname, lastname){
    var fullname = firstname + ' ' + lastname;
    return fullname;
}
```

So now you can use `getFullName()`
```javascript
document.getElementById('displayBox').innerText = getFullName('Jessica', 'Smith');
```

What happens if you don't pass arguments to a function that expects them?  The parameters won't be initialised, just like an uninitialised variable.  They will have the value of `undefined`.

What happens if you pass arguments to a function without declared parameters?  Nothing.

What happens if you pass arguments of a different type than what the function expects?  Depends on the function and what it is doing with them.

TIP: `undefined` evaluates to `false` in a boolean expression.  So you could use this to check if a given parameter was passed a value.

```javascript
function getFullName(firstName, lastName){
  // first name only: fname
  // lastname only: [unknown] LastName
  // neither: [unknown]
  var lname = '';
  var firstname
  if(!lastName){ lname = '[unknown]'; } else lname = lastName;


  if(!firstName){ fName = ''; } else { fName = firstName; }
  if(!lastName){ lName = ''; } else { lName = lastName; }

  if(!fName && !lastName){
    fullName = 'Jane/John Doe';
  } else {
    fullName = firstName + ' ' + lastName;
  }
  return fullName;
}
```

## Chaining


---
What makes up a function?

* A function usually has a name.  This is a bit like the variable name for the function.  There are cases where a function doesn't have a name, an **anonymous** function.
* A function can have values passed into it which become variables in the body.  These are called parameters or arguments depending on the context.  People often use these terms interchangeably so don't worry about getting them confused. :-)  
* The function body is the code that is run when the function is run.
* A function can **return a value**.  


<!-- * elements?
  * name
  * parameters
  * body
  * return value -->

<!-- 3. syntax for declaring a function -->

<!-- 4. syntax for invoking a function -->

---

Function are also how a lot of features are exposed by the browser, like the DOM API.

Functions save you time (write once, use many times) and they help you organise your programs so its easier to understand.
They make your programs more flexible and easier to change (and fix) in the future.

We've actually created and used functions several times already.

Creating a function is called **declaring** it.

Running a function is called **invoking** or **calling** it.


## Declaring Functions

There are a couple of different ways of declaring functions, the easiest is with the `function` keyword.
We've done this already with `setArrive`, `setLeave`, and `sayStuff`.

```javascript
function setArrive(){
  message = 'Welcome!';
}
```

To declare a function:

1. start with the `function` keyword,
2. then the name of your function,
3. opening and closing parentheses,
4. and then the code for your function between opening and closing braces



<!--
 without explaining them, so let's do that now.


We use functions for useful for a few different things.


4. functions used in Javascript to attach behaviour to events, like clicking on buttons.

We've actually already used functions multiple times so far.

We've declared three functions: `setArrive`, `setLeave`, and `sayStuff`, and we've attached them to `onclick` events.

We've also used functions that we didn't write, specifically `getElementById`.

However there are two features of functions, **arguments** and **return values** that we haven't used in our functions yet.

Lets update our program to address us by name, and to be a little more flexible. -->


Let's review our program:

```javascript
var message = "I don't know where you are!";

function setArrive(){
  message = 'Welcome!';
}

function setLeave(){
  message = 'Farewell my friend!';
}

function sayStuff(){
  document.getElementById('displayBox').innerText = message;
}

document.getElementById('sayButton').onclick = sayStuff;
document.getElementById('arriveButton').onclick = setArrive;
document.getElementById('leaveButton').onclick = setLeave;
```





"Group sets of instructions together so they can be use like a single instruction"

Functions allow us to take a series of instructions from our program, give them a name, and then perform those steps

As we said earlier, think of your program as a todo list for the computer.  
However because we have to tell the computer every single step, these lists can get very long and often end up repeating multiple steps many times.

Functions let us take one or more instructions from our program, separate them from the main program and assign them a name.  
Then every time we want to perform those steps in our program well tell it to use that function.


---

Functions are how we break up our program into smaller pieces that we can then reuse.

If we need our programs to repeat the same tasks in multiple places, functions let us do that without having to repeat our code multiple times.

By having our programs made of smaller pieces that are reused, it's easier to make changes in the future and fix bugs.

Javascript also uses functions to assign behaviour to different events in the browser like clicking on specific elements.
Which is what we've been doing so far with our three functions, `setArrive`, `setLeave`, and `sayStuff`.  

Let's revise our application so it also displays the appropriate message when you click the `Arrive` and `Leave` buttons.



the various different steps of our program.

To use the todo list metaphor, functions are like little todo lists.

Instead of repeating a specific set of steps the time you put those steps into a function and can simply add a step that says "do the steps in this specific function".

In Javascript, functions are also how we tell the browser what steps to carry out when different events happen, like clicking on a button.
We've already been doing that.
