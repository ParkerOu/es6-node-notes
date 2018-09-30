# Arrow function
 > Also known as lambda expression (a function without a name)
 ```js
 let sum = function (a, b) {return a + b};
 let add = (a, b) => a + b;

 console.log(sum(3,6)); // 9
 console.log(add(3,6)); // 9
 ```
 ```js
 let greeting = () => "How's your day?";
 function greet() {
     return "How's your day?";
 }

 console.log(greeting()); // How's your day?
 console.log(greet()); // How's your day?
 ```
 ## Example
 ```js
let points = [1, 3, 5];

let addOne = function(element) {
    return element + 1;
}
points = points.map(addOne);
console.log(points); // [2, 4, 6]

points = points.map(element => element + 1);
console.log(points); // [3, 5, 7]
 ```
 ## Arrow function ignore **this**
 ### Normal function
```js
this.color = 'blue';

let showcolor = function () {
    console.log('color', this.color);
}
showcolor(); // color undefined
```
```js
this.color = 'blue';

let showcolor = function () {
    this.color = 'green';
    console.log('color', this.color);
}
showcolor(); // color green
```
### Arrow function
```js
this.color = 'blue';

let arrowshow = () => {
    console.log('this.color in arrow function:', this.color);
}
arrowshow(); // this.color in arrow function: blue
```
## Filter
### Normal function
```js
let isPass = (grade) => {
    return grade >= 60;
}

let scores = [73, 52, 69, 43, 90, 77, 59, 81];
let passing = scores.filter(isPass);
console.log(passing); // [73, 69, 90, 77, 81]
```
### Arrow function
```js
let scores = [73, 52, 69, 43, 90, 77, 59, 81];
let passing = scores.filter(element => element >= 60);
console.log(passing); // [73, 69, 90, 77, 81]
```