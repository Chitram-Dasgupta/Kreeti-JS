---
title: JavaScript Assignment 4
author: Chitram Dasgupta
---

# Question 1

Given a string “Azad Ram Madiha Yash”. Return a string with the first letter of every word from the string. (Use built in methods).

## Answer

```js
const my_str = 'Azad Ram Madiha Yash';
const new_str = my_str.split(' ').map(x => x[0]).join('');

console.log(new_str);
```

# Question 2

Given an array [1, -4, 12, 0, -3, 29, -150]. Calculate the sum of all positive numbers (use built in array methods).

## Answer

```js
const my_arr = [1, -4, 12, 0, -3, 29, -150];

const res = my_arr.filter(x => x > 0).reduce((acc, curr) => acc + curr, 0);
console.log(res)
```

# Question 3

Given an array [1, 2, 3, 4, 5]. Create a new array with the square of each element(use built in array methods).

## Answer

```js
const my_arr = [1, 2, 3, 4, 5];

const new_arr = my_arr.map(x => x ** 2);
console.log(new_arr)
```

# Question 4

Given an array [{ id: 2100, name: 'President Jacqueline' }, { id: 2114, name: 'Vice-president James' }, { id: 3016, name: 'House-captain Otis' },  { id: 4818, name: 'Prefect Finneas' }]. Create an array containing just the id of every individual. (write two solution one using iterator and another using built-in method)

## Answer

### Using iterator

```js
const my_arr = [
  { id: 2100, name: 'President Jacqueline' },
  { id: 2114, name: 'Vice-president James' },
  { id: 3016, name: 'House-captain Otis' },
  { id: 4818, name: 'Prefect Finneas' }
];

const ids = []
for (const i of my_arr) {
  ids.push(i.id)
}

console.log(ids)
```

### Using built-in method

```js
const my_arr = [
  { id: 2100, name: 'President Jacqueline' },
  { id: 2114, name: 'Vice-president James' },
  { id: 3016, name: 'House-captain Otis' },
  { id: 4818, name: 'Prefect Finneas' }
];

const ids = my_arr.map(e => e.id);
console.log(ids);
```
