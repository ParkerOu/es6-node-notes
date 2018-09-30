# Spread Operator
> **Spread Operator** is a syntactic sugar for "expanding an array into individual values."
```js
let params = [ "hi", true, 7 ]
let other = [ 1, 2, ...params ] // [ 1, 2, "hi", true, 7 ]

let str = "foo"
let chars = [ ...str ] // [ "f", "o", "o" ]
```
# Rest parameters
> Represent an indefinite number of arguments as an array
>> Must put in the last position
```js
function sum(...numbers) {
  let result = 0;
  numbers.forEach(function (number) {
    result += number;
  });
  return result;
}
console.log(sum(1)); // 1
console.log(sum(1, 2, 3, 4, 5)); // 15
```
# Destructing Assignment
```js
let num = [172, 58];
let [height, weight] = num;
console.log(height, weight); // 172 58
```
```js
let arr = [1, 2, 3, 4, 5];
let [a, ...b] = arr;
console.log(a); // 1
console.log(b); // [2, 3, 4, 5]
```
## Destructing Assignment(Object)
```js
let wedding = {expensive: true, joyness: 9};
// let expensive = wedding.expensive;
// let joyness = wedding.joyness;
let {expensive, joyness} = wedding;
console.log(expensive, joyness); // true 9
```
- use () to assign already exist let variable.
```js
let expensive = true;
let joyness = 1;
let wedding = {expensive: false, joyness: 99};

({expensive, joyness} = wedding);
console.log(expensive, joyness); // false 99
```