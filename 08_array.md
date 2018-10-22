# Basic Iterate
### 1. for-loop
```js
let arr = [1, 2, 3];

for (let index in arr) {
    console.log(arr[index]);
}
```
### 2. forEach (array built in function)
```js
let arr = [1, 2, 3];

arr.forEach(function(element) {
    console.log(element);
});
```
### 3. [map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
> Process all element in the array, and return a new one. (Original array won't change)
```js
let arr = [1, 2, 3];

// pass a function to map
const afterArr = array1.map(x => x * 2);

console.log(afterArr);
// output: Array [2, 4, 6]
```
```js
let gradeArr = [81, 130, 75, 77, 95, 92, 177, 99, 222];

let newArr = gradeArr.map(function(grade){
  if(grade >= 100) {
    return 100;
  }
  return grade;
});
console.log(newArr);
// output: [81, 100, 75, 77, 95, 92, 100, 99, 100]
```
### 4. [reduce()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)
> Process all element in the array, and return a single value. (Original array won't change)
```js
let arr = [1, 2, 3, 4];

let result = arr.reduce(function(prev, element) {
  return prev + element;
});

console.log(result);
// output: 10
```
```js
var arr = [
    'Python',
    'JavaScript',
    'Java',
    'JavaScript',
    'JavaScript',
    'Python',
    'C'
];

// calculate language appear n times
let langStatistics = arr.reduce(function(langs, langName) {
    if (langs.hasOwnProperty(langName)) {
        langs[langName]++;
    } else {
        langs[langName] = 1;
    }
    
    return langs;
}, {});

console.log(langStatistics);
// output: {Python: 2, JavaScript: 3, Java: 1, C: 1}
```
### 5. [Object.values]('https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/values')
> return an array of values.
```js
const myShoes = {
    brand: 'SKECHERS',
    price: 60,
};

Object.values(myShoes);
// output: ["SKECHERS", 60]
```

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