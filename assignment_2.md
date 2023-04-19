---
title: JavaScript Assignment 2
author: Chitram Dasgupta
---

# Question 1

If we execute this Javascript, what will the browser's console show?

```js
var text = 'outside';
function logIt(){
    console.log(text);
    var text = 'inside';

};

logIt();
```

## Answer

The browser console will show `undefined`. This is because, inside the scope of
the function, the `var text` declaration will be *hoisted* to the top of the
function. As a result, the call to `console.log()` will print `undefined`.
The assignment will occur after the call to `console.log()`.

# Question 2

Write a regular expression  to reverse the first and last name

## Answer

```js
let name = "John Smith";
let reversedName = name.replace(/^(\w+)\s+(\w+)$/, "$2 $1");
console.log(reversedName); // Output: Smith John
```

The regular expression matches a string that starts with one or more word
characters `^(\w+)`, followed by one or more whitespace `\s+`, and ends with
one or more word characters `(\w+)$`.

# Question 3

Write a regular expression  to reverse the first and last name

## Answer

```js
let email = "Chitram.Dasgupta@kreeti.com";
let isValidEmail = /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);
console.log(isValidEmail);
```

This outputs `true`.

Using the regular expression, we match strings what start with one or more
characters that are not whitespace and '@' (`^[^\s@]+`), followed by `@`,
which is further followed by one or more characters excluding whitespace and
'@' (`[^\s@]+`), then it has a `.`, and the string ends with one or more
characters, excluding whitespace and '@' (`[^\s@]+$`)

# Question 4

Find the Output

```js
var x = 100;
console.log(x);

function test(){
  var x = 250;
  console.log(x);

  if (x > 100) {
    let x = 350;
    console.log(x);
  }

  console.log(x);
}

test();
console.log(x);
```

## Answer

This will print the following:

```
100
250
350
250
100
```

`100` will be printed as the first `console.log(x)` is preceded by `var x = 100`.
Then, same inside the function `200` will be printed and inside the *if-block*,
`let x = 350` will make `console.log(x)` print `350`. Now, `let x = 350` is scoped
to the *if-block* because we used `let`. As a result, it will be unavailable outside
the *ig-block*. As a result, the `console.log(x)` outside the *if-block*, will print
`250`. Finally, `console.log(x)` will print `100` because only `var x = 100` is
globally-scoped.

# Question 5

What is the difference of output between these two expressions? Give your reasons for it:

a. 12 == “12”

b. 12 === “12”

c. Number(12) === 12

## Answer

a. `12 == '12'` will return `true`, because `==` will only compare the value.

b. `12 === '12'` will return `false`, because `===` compares the value as well as the datatype(which differs here, one is a number and the other a string)

c. `Number(12) === 12` will return `true` because even though `Number(12)` returns a number object,
the `===` operator will attempt *type-coercion*, which will succeed. As a result, the comparison will
be done on the value and type of the number primitive 12, which indeed will return `true`.
