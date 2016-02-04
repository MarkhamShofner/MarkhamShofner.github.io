---
layout:     post
title:      Approaching Problems
date:       2016-01-04 04:25:00
author:     Markham Shofner
summary:    Math math math
categories: Javascript
tags:
 - math!
---

What follows is a mental framework you can use to solve seemingly complex problems. In this case, we will work through solving a mathematics question by using JavaScript as a tool, but more importantly, our ability to parse out simple questions within a larger more complex unifying question.    
Ok. So last time we covered the basics of a Project Euler problem. Let's use this post to explore good practices for working through a more advanced problem. In this case, problem #6 from that same site.    
Project Euler - problem 6  
***
The sum of the squares of the first ten natural numbers is,
12 + 22 + ... + 102 = 385
The square of the sum of the first ten natural numbers is,
(1 + 2 + ... + 10)2 = 552 = 3025
Hence the difference between the sum of the squares of the first ten natural numbers and the square of the sum is 3025 − 385 = 2640.
Find the difference between the sum of the squares of the first one hundred natural numbers and the square of the sum.
***

Typically, it makes sense to understand a problem on a solely verbal level before you begin coding. A few questions that are useful to have full, or at least partial, answers to:

1. What is the final purpose of the code?
2. What are the main component vectors needed to get there?
3. What are hurdles or likely glitches that should be avoided?
4. What are the first steps required to get moving?

Some basic answers for this problem are:

1. Here the final goal is code that answers to the question "what is the difference between the sum of the squares of the first one hundred natural numbers and the square of the sum". Ideally, the code is dynamic enough that you can answer many similar questions. So not just "the first hundred" but maybe "the first thousand" or "the first twenty" as well.
2. Primary components needed are mechanisms to
  - Calculate the sum of the squares
  - Calculate the square of the sum
  - Calculate the difference
3. Hurdles could be anything. In my case, I sometimes have to rescope my variables when I am not careful initially. And since I will be using a few variables here, I'll keep an eye on that.
4. Set up my pseudocode before any true lines of code.

Following step four (and using the components discussed in step 2). Provide your pseudocode. Mine looks something like this.  
// function to return the square of an input integer x  
// function to sum the squares from 1 to input integer x  
// function to square the sum from 1 to input integer x  
// function to find the sum square difference for an input integer x

One could probably combine parts of these functions together (particularly something as simple as the square of an input integer), but personally I like breaking my functions out as much as possible, and I suggest you do the same. Unless you're Ender Wiggin.

Expanding my first piece of pseudocode I would write a function to achieve the stated goal.  
// function to return the square of an input integer x
Mine looks like this

```javascript
function square (x) {
  return x*x;
}
```
What does yours look like?

Next we can expand  
// function to sum the squares from 1 to input integer x

```javascript
function sumSquare (x) {
  var sum = 0;
  for (var i = 1; i<=x; i++) {
      sum += square(i);
    }
  return sum;
}
```
Here I used a for loop to determine the sum of all squares between 1 and the inputted value.

Then we'll work through  
// function to square the sum from 1 to input integer x

```js
function squareSum (x) {
  var sum = 0;
  for (var i = 1; i<=x; i++) {
    sum += i;
  }
  return square(sum);
}
```
This function has a similar logic to the preceding one.

Finally, we can write a short function that combines the above two functions to calculate the difference between the two. Does yours look like this?  
// function to find the sum square difference for an input integer x

```js
function sumSquareDif (x) {
  return squareSum(x) - sumSquare(x);
}
```

In all functions, I suggest that you test each as you go, to make sure that the function is actually outputting what you expect. I primarily rely on console.log() for this purpose.

In the end, here is my uncommented code ---

```js
function square (x) {
  return x*x;
}
function sumSquare (x) {
  var sum = 0;
  for (var i = 1; i<=x; i++) {
    sum += square(i);
  }
  return sum;
}
function squareSum (x) {
  var sum = 0;
  for (var i = 1; i<=x; i++) {
    sum += i;
  }
  return square(sum);
}
function sumSquareDif (x) {
  return squareSum(x) - sumSquare(x);
}
```
---
A simple
console.log(sumSquareDif (100));
Will return the answer. What did you get? Test your answer on projecteuler.net!

That is just my own code though. The idea is that you can apply similar principles to solve many of your coding problems. Not just fun mathematics ones pre-provided by Project Euler.

In the New Year's spirit, and one of developing good habits, and cultivating efficient patterns, let us remember that -

> We tend to repeat those things we have repeated."

	- David Marmet
