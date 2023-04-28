---
title: JavaScript Assignment 5
author: Chitram Dasgupta
---

# Question 1

What is an IIFE (Immediately Invoked Function Expression) and why would you use
it in JavaScript? Give an example of IIFE.

## Answer

An Immediately Invoked Function Expression (IIFE) is a JavaScript function that
is executed immediately after it's defined.  IIFEs are often used to create a
private scope for variables and functions, which helps prevent naming conflicts
and improves code organization.

```js
(function() {
  console.log('Hello, world!');
})();
```

# Question 2

What is the purpose of using the bind() method in JavaScript and how is it
different from call() and apply()?

## Answer

In JavaScript, the `bind()`, `call()`, and `apply()` methods are used to set the value
of `this` inside a function, and to pass arguments to the function. The `bind()`
method creates a new function with the same body as the original function, but
with a fixed this value and possibly some arguments. The `call()` and `apply()`
methods invoke the function with a given this value and arguments.

```js
const person = {
  firstName: 'John',
  lastName: 'Doe',
  fullName: function() {
    return this.firstName + ' ' + this.lastName;
  },
  greet: function(greeting) {
    console.log(greeting + ', ' + this.fullName() + '!');
  }
};

const boundGreet = person.greet.bind(person, 'Hello');
boundGreet(); // outputs "Hello, John Doe!"

person.greet.call(person, 'Hi'); // outputs "Hi, John Doe!"

person.greet.apply(person, ['Bonjour']); // ouputs "Bonjour, John Doe!"
```

`bind()` creates a new function with a fixed this value and any additional
arguments, without actually invoking the function. `call()` and `apply()` both
invoke the function with a given this value and arguments, but `call()` takes
arguments directly, while `apply()` takes an array of arguments.

# Question 3

What is a Higher-Order Function (HOF) in JavaScript and how is it different from
regular functions? Explain with an example.

## Answer

A Higher-Order Function (HOF) is a function that either takes one or more
functions as arguments, or returns a function as its result. HOFs are different
from regular functions in that they operate on other functions rather than data.

```js
function greeting(name, greetFunc) {
  return greetFunc(name);
}

function sayHello(name) {
  return 'Hello, ' + name + '!';
}

console.log(greeting('World', sayHello)); // outputs "Hello, World!"
```

# Question 4

Write a function called multiplyBy that takes a number as input and returns a
new function that multiplies any number passed into it by the original number.

## Answer

```js
function multiplyBy(num) {
  return function(x) {
    return num * x;
  }
}

const double = multiplyBy(2);
const triple = multiplyBy(3);

console.log(double(5)); // outputs 10
console.log(triple(5)); // outputs 15
```

# Question 5

Write a function named sortArray that takes in two parameters:

1. An array of numbers

2. A boolean value ascending that indicates whether the array should be sorted
   in ascending or descending order.

The sortArray function should return the sorted array. Use an anonymous function
to do the actual sorting, rather than using the built-in sort method.

## Answer

```js
function sortArray(arr, ascending) {
  const sortFn = function(a, b) {
    if (ascending) {
      return a - b;
    } else {
      return b - a;
    }
  };

  for (let i = 0; i < arr.length - 1; i++) {
    for (let j = i + 1; j < arr.length; j++) {
      if (sortFn(arr[i], arr[j]) > 0) {
        const temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
      }
    }
  }

  return arr;
}

const arr = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5];
console.log(sortArray(arr, true)); // outputs [1, 1, 2, 3, 3, 4, 5, 5, 5, 6, 9]
console.log(sortArray(arr, false)); // outputs [9, 6, 5, 5, 5, 4, 3, 3, 2, 1, 1]
```
