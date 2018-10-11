# Usage
## We could use single quote or double quote
```js
let s1 = "Let's get started!"; // When String contains single quote('), use double quote("")
let s2 = 'JS is cool.';
```
## Escape special character
```js
let s3 = "Learn JS \"in one day\"."; // use \ to escape
console.log(s3);
// output: Learn JS "in one day".
```

# Template Strings
## 1. use +
```js
let name = 'Parker';
let habbit = 'coding';
console.log('My name is ' + name + ', I love ' + habbit); 
```
## 2. use back-tick(\` `)
```js
console.log(`My name is ${name}, I love ${habbit}`);
```

# Useful function & attribute
- [length](https://www.w3schools.com/jsref/jsref_length_string.asp) returns the length of a string
```js
let sayhi = 'Hello JS!'
console.log(sayhi.length);
// output: 9
```
> stringObject.replace(regexp/substr, replacement)
- [replace()](https://www.w3schools.com/jsref/jsref_replace.asp) returns a new string where the specified values are replaced
```js
let str = 'impossible';
console.log(str.replace('im', "I'm "));
// output: I'm possible

str = 'Willy love dogs. Willy also lvoe cats.';
console.log(str.replace('Willy', 'Parker'));
// output: Parker love dogs. Willy also lvoe cats.
console.log(str.replace(/Willy/g, 'Parker'));
// output: Parker love dogs. Parker also lvoe cats.
```
> **g** means golbal stating<br />
> **i** means case insensitive 
- toUpperCase() / toLowerCase()
```js
let s = 'I love JS.';
console.log(s.toUpperCase());
// output: I LOVE JS.
console.log(s.toLowerCase());
// output: i love js.
```
- [split()](https://www.w3schools.com/jsref/jsref_split.asp) returns an array of substrings
```js
let fruits = "apple,banana,guava";
console.log(fruits.split(','));
// output: ["apple", "banana", "guava"]

let colors = "red green blue";
console.log(colors.split(' '));
// output: ["red", "green", "blue"]
```