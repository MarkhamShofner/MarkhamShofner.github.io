---
layout:     post
title:      Project Euler
date:       2015-11-10 03:31:00
author:     Markham Shofner
summary:    Exploration of some basic math problems.
categories: web development, mathematics
tags:
 - education
 - math!
---

Let me introduce you to something I love - behavioral languages, in this case JavaScript. I love making things happen with code! I love conditional statements, and for loops. Here is an example of solving a simple math problem using code - from one of my favorite websites, [Project Euler] (https://projecteuler.net/). I encourage you to try some of these on your own. They are fun, logical, and educational.

Problem 1 - Multiples of 3 and 5
If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.
Find the sum of all the multiples of 3 or 5 below 1000.

The code I used -

```js
//Project Euler - Problem 1
//Find the sum of all the multiples of 3 or 5 below 1000.

//create an integer variable named "sum" that initializes at 0. this variable will be used to hold the sums
var sum = 0;

//top end of the range to sum across, 1000 in the case of this problem
var range = 1000;

//for loop to test if the acting number is a multiple of 3 or 5, and then add the # to sum. this text after for and within the () means to start looping at 0, continue looping while "i" is less than "range" [1000 in this case], and to increase the count of "i" by 1 at the end of each loop iteration [i++]
for (var i=0; i<range; i++) {
// this section says to execute the code inside the curly brackets, if i%3 === 0. i%3 returns the remainder of i/3. if i%3 === 0, then i is divisible by 3. so basically, if i is divisible by 3, execute the contained code.
if (i % 3 === 0) {
// if this code is reached, it means the i is divisible by 3 in which case, we want to add i to the current total for our sum variable. this line of code basically assigns "sum" to "sum + i"
sum += i;
}
// using the same logic as above, except in this case, if the first conditional isn't met (meaning i%3 does not equal 3), the script will check if i is divisible by 5. if so, it will execute the contained code
else if (i % 5 === 0) {
// if this code is reaached, it means that is divisible by 5, and was not divisible by 3. if i was divisible by 3, the script will jump to the end of the if/else conditional. the below line of code assigns "sum" to "sum + i".
sum += i;
}
// if neither of the previous conditions are met (in this case, i being divisible by 3 or 5), then the code within these brackets will be executed. since we only want to increase our "sum" variable, if "i" is divisible by 3 or 5, we want to leave these brackets empty.
else {}
//once the end of the loop is reached, "i" will increase by 1, and the loop will run again
}

// return the current value of the sum variable
sum;
```

In the end, it's a fairly simple concept. There is so much power to it though. What if, instead of calculating through 10 (which could be done by hand), we needed to calculate through 1,000 (as in this problem), or 10,000,000 (which could take a lifetime). Computers can return these figures in incredibly short amounts of time. We simply need to learn how to ask them to.

As Tyrion says “My brother has his sword, King Robert has his warhammer and I have my mind...and a mind needs books as a sword needs a whetstone if it is to keep its edge. That's why I read so much Jon Snow.” Except replace books with coding problems, and Jon Snow with you. Also R+L=J, naturally. And, again naturally, this means that R=J-L, and the corollary that (R+L)/J = 1.

>Sleep is good, and books are better.

	- Tyrion Lannister
