---
layout: step
number: 4
title: Array
permalink: step4/

# keywords:
#  - term: package.json
#    define: A `package.json` is the file used to store information about a Node.js project, such as its name and its dependencies. Read more [here](https://docs.npmjs.com/files/package.json).

---

We often want to repeat specific steps in our programs at certain times.

And we don't always know exactly how many times.

We call this **looping** and there are many different ways to do it.

We are going to look at the `for` loop and array loops.

## The `for` loop

The `for` loop is used to repeat steps with a counter.  

Let's create a simple app where you specify a message and a number and the message gets displayed that number of times.

<!-- You set the initial state of the counter at the beginning, specify the condition to stop at, and how to   -->

```html
<input type="text" id="theMessage" placeholder="What message?"/>
<input type="text" id="howMany" placeholder="Repeat how many times?"/>
<button id="goButton">Go</button>
<pre id="displayBox" />

<script>
function showMessage(){
  var howManyTimes = document.getElementById('howMany').value;
  var message = document.getElementById('theMessage').value;

  var output = '';
  for(var i=0;i<=howManyTimes;i++){
    output = output + '<p>'+message+'</p>';
  }
  document.getElementById('displayBox').innerText = output;
}
</script>
```

Let's look at the loop in more detail:
```javascript
for(var i=0;i<=howManyTimes;i++){
  output = output + message+'\n';
}
```

There are two main parts:

1. The loop declaration, `for(var i=0;i<=howManyTimes;i++)`

  The loop declaration looks a bit like a function invocation,  but it isn't.  It defines how the loop will behave.

2. The loop statement block.

  The statement block is the steps to perform each time the loop repeats.

The declaration has the `for` keyword and three semicolon separated expressions inside the parentheses to define it.  

1. The first expression is the initialiser:`var i=0`

  This is run before the loop starts and is used to setup anything we need to track the loop.

  In this case, we create a counter to track how many times the loop as run.

2. The second expression is the condition: `i<=howManyTimes`

  This is evaluated at the beginning of each loop and the statement block only runs if it evaluates to `true`.  If it is `false` the block doesn't run and the loop ends.  

  So for our example it means that while the value of `i` is less than or equal to `howManyTimes` the loop continues.
3. The third expression is the final expression.  This is performed after each time the statement block runs.
