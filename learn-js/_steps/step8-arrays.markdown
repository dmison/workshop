---
layout: step
number: 4
title: Array
permalink: step4/
requires:
  - objects
  
# keywords:
#  - term: package.json
#    define: A `package.json` is the file used to store information about a Node.js project, such as its name and its dependencies. Read more [here](https://docs.npmjs.com/files/package.json).

---

Arrays are special type of object which contains an ordered list of values.
We often end up having to keep lists so arrays are really useful.  


You can create an array like this:

```javascript
var catNames = ['Garfield', 'Felix', 'Azrael'];
```

You can also start with an empty array like this:

```javascript
var catNames = [];
```

Arrays are **index** based lists.  This means you can refer to each item in the array using it's position or index.

Array indexes start at zero, so the first item is item 0, the second one is at 1 and so on.

To look up a value in an array you use it's index.

```javascript
var name = catNames[1];
```

This assigns the value of the second item in the `catNames` array (ie `'Felix'` to the name variable.

To change the value

## Mixing types in an array is almost always a bad idea.

Not all values in an array have to be the same type, but it is a good idea.
It can get confusing if your arrays contain different types.
If you find yourself wanting different types in an array, you might want to ask yourself why and consider alternatives.

For example if you wanted to keep a list of the cat names & their colours you might be tempted to do something like this:

```javascript
var catNamesColours = ['Garfield', 'Orange','Felix', 'Black & white', 'Azrael', 'Brown'];
```

You *could* write code to remember that the names are at index `0` and the even ones, and the item after the name is the colour for that cat. It's really easy to make a mistake here.

A better idea would be to make cat objects to hold the information and keep those in the array.  

```javascript
var cats = [
  {
    name: 'Garfield',
    colour: 'Orange'
  },
  {
    name: 'Felix',
    colour: 'Black & white'    
  },
  {
    name: 'Azrael',
    colour: 'Brown'
  }
]
```

It almost always make sense to only use a single type in an array.


Arrays also have a bunch of properties that expose information about the list it has as well as functions to let you easily manipulate that list.
