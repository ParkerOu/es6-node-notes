# [Console](https://developer.mozilla.org/zh-TW/docs/Web/API/Console)
### 1. console.log
Must commonly used. Print the results to debug.
```js
let someObject = { str: "Some text", id: 5 };
console.log(someObject); 
// output: {str: "Some text", id: 5}

console.log(3 + 5);
// output: 8
```
### 2. console.time
Calculate the duration of a specific operation.
```js
console.time("answer time");
alert("Click to continue");
// some function
console.timeEnd("answer time");
```
### 3. console.table
Displays tabular data as a table.
```js
const Willy = { name: 'Willy', age: 20, handsome: false };
const Parker = { name: 'Parker', age: 23, handsome: true };
const Sam = { name: 'Sam', age: 25, handsome: false};

console.table([Willy, Parker, Sam]);
```
<table>
  <tr>
    <td>(index)</td>
    <td>name</td>
    <td>age</td>
    <td>handsome</td>
  </tr>
  <tr>
    <td>0</td>
    <td>Willy</td>
    <td>20</td>
    <td>false</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Parker</td>
    <td>23</td>
    <td>true</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Sam</td>
    <td>25</td>
    <td>false</td>
  </tr>
</table>