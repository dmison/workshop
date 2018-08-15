---
layout: step
number: 5
title: Conditions
permalink: step5/

# keywords:
#  - term: package.json
#    define: A `package.json` is the file used to store information about a Node.js project, such as its name and its dependencies. Read more [here](https://docs.npmjs.com/files/package.json).

---

We don't always want our programs to perform the exact some series of steps every time.
Often we want different actions to occur based on user input or other information.

We refer to this as our code having **branches** or more than one **path**.

**Conditional statements** (or conditionals) are how we control which paths our programs will follow when they run.

The most common conditional is the `if` statement.

Here's an example that checks if the user had supplied a first name and sets an error message if they hadn't.

```Javascript
if(firstName == ''){
  errorMessage = 'You must enter your first name';
}
```

There are two basic parts to an `if`:

 * the condition in parentheses, which is the question being asked
 * and the code block in braces, which is what to do if the answer to the question is yes.

Optionally you can add an `else` and another code block to be run if the condition is not met.

The condition is assumed to be what we call a **boolean expression**.
Boolean expressions are expressions that get evaluated to one of two special values: `true` or `false`.
This is done using special operators called **comparison operators**.

The boolean operator used above (`==`) is called the **equality operator** AKA the **is equal to** operator.
If the values on both sides of it are considered equal then the expression evaluates to `true`.
If they aren't equal then the expression is `false`.

## Using Conditionals

Let's update our code so we can tell the page our name, and it can use that name to address us.

First update `index.html` to add a box that we can type our name into:

```html
<input type="text" id="nameInput" placeholder="Type your name here" />
```

Now lets's update our javascript so our `setLeave` and `setArrive` functions get what we have typed into the box and include it in the message.

```Javascript
function handleArrive(){
  var name = document.getElementById('nameInput').value;
  message = 'Welcome '+name+'!';
}

function handleLeave(){
  var name = document.getElementById('nameInput').value;
  message = 'Farewell '+name+'!';
}
```

Ok, refresh the page, type a name into the box, click `arrive` or `leave`.

[SCREENSHOT]

But wait, we have a subtle problem.
What if you don't type in a name?
Your message will just have a blank name, which isn't great.

So let's fix that by using conditionals to tell our code what to do in that case.

```Javascript
function handleArrive(){
  var name = document.getElementById('nameInput').value;
  if(name == ''){
    message = "Welcome stranger!  What's your name?";
  }
  else {
    message = 'Welcome '+name+'!';
  }
}

function handleLeave(){
  var name = document.getElementById('nameInput').value;
  if(name == ''){
    message = 'Farewell mysterious stranger!';
  }
  else {
    message = 'Farewell '+name+'!';
  }
}
```

Here we are using an else block.

If `name` is an empty string we set `message` to string that does not include `name`.

If `name` is not an empty string then the `else` block will run and it sets `message` to a string with `name` concatenated with `+`.

So now `handleArrive` and `handleLeave` both have two different **paths of execution**.  

(
`handleArrive` and `handleLeave` do almost exactly the same steps, with subtle differences.  
You might be wondering if there is a better way to handle this so you aren't writing almost the same code over and over.
Yes there is, we use functions for that which we will talk about about in the next step.
)

## Comparison Operators

So far we've seen the `==` comparison operator, the **is equal to** operator.

| Operator | Name/Description | Applies to |
|-|-|-|
| `==` | Equality.  Both sides must be equal.  | Numbers & Strings. |
| `===` | Strict equality. Value & type must both be the same.| Numbers & strings.|
| `!=` | Inequality.  Both sides must be different.  | Numbers & strings. |
| `!==` | Strict inequality. Different values OR different types. | Numbers & strings.|
| `<` | Less than.  | Numbers. |
| `>` | Greater than.  | Numbers. |
| `<=` | Less than or equal to.  | Numbers.  |
| `>=` | Greater than or equal to.  | Numbers. |

These are all pretty obvious with the exception of the strict equality & inequality.  

The non-strict versions (`==` & `!=`) will try to convert the types of the values if they are different before comparing them.  For example `12 == '12'` is treated as `'12' == '12'`.

The strict versions will not do the type conversion.

It is generally recommended to use the strict versions of these operators.

## Logical Operators

There is also a set of **logical operators**, which you can use when you need to test multiple things as a single condition.

The most commonly used logical operators are: **NOT** (`!`), **AND** (`&&`), and **OR** (`||`).

### The AND operator `&&`
The AND operator, `&&`, is used when multiple conditions must all be `true`.  

Here, `name` would be the string they typed in, and `tickedAgree` is a boolean (`true` or `false`) as to whether they ticked a checkbox.

```Javascript
if(name !== '' && tickedAgree){

}
```

You can add as many conditions as you want with `&&` and it will check each one in turn until it finds one that is false at which point it considers the whole expression false.

Note that you can test boolean variables or values into conditions without having to use `=== true` because they already are true or false.


### The OR operator `||`

The NOT operator, `!`, is used to reverse a boolean value.  It turns something that is `true` into `false` and vice versa.  To use it you prefix the variable or before a parentheses you want to reverse.


### The NOT operator `!`

All of this is related to a special field of mathematics called [boolean algebra](https://en.wikipedia.org/wiki/Boolean_algebra).
You don't need to be an expert on boolean algebra to be a programmer, but it is an interesting area.
Learning a little bit about the basics can help you in the long term, but don't lose any sleep over it now.
