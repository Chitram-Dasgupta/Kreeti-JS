---
title: JavaScript Assignment 1
author: Chitram Dasgupta
---

# Question 1

Write a program that declares a variable using var, let, and const and prints the value to the console.

## Answer

```js
var x = 10

let y = 20

const z = 30

console.log(x)
console.log(y)
console.log(z)
```

# Question 2

Write a program that reassigns a value to a variable declared with let and prints the new value to the console.

## Answer

```js
let x = 10

x = 20

console.log(x)
```

# Question 3

Write a program that tries to reassign a value to a variable declared with const and prints the message to the console

## Answer

```js
const x = 10

x = 20 // This will throw error

console.log(x)
```

We cannot re-assign a variable declared with const. This is why we get the error.

# Question 4

Write a program to declare a const, let, var variable within an if statement and try to access the variable outside the if block, what is the result?

## Answer

```js
if (5 > 3) {
  var x = 10
  let y = 20
  const z = 30
}

console.log(x)
console.log(y) // Error
console.log(z) // Error
```

Variables declared with let and const are scoped to the block they are declared in.
This is why when we try to access them outside the if-block, we get an error.

# Question 5

Write a program that concatenates two or more strings and prints the result to the console.

## Answer

```js
const first = 'Hello'
const second = 'World'

const res = `${first} ${second}`

console.log(res)
```

# Question 6

Write a program that takes a string as input and prints the length of the string to the console.

## Answer

```js
const prompt = require('prompt-sync')();

const inp = prompt('What is your name?');
console.log(inp.length);
```

# Question 7

Write a program that converts a string to uppercase and prints the result to the console.

## Answer

```js
let my_str = 'hello'
let res = my_str.toUpperCase()

console.log(res)
```
