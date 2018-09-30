# Const & let
## variable -> use let 
### 1. let is block scope
```js
let height = 172;
console.log(height);
// output: 172
{
    let weight = 58;
    console.log('in the block: ' + weight);
    // output: 'in the block: 58'
}
cosole.log('outside: ' + weight);
// GET SOME ERROR!
```
### 2. let can't declare twice (in same scope)
```js
let name = 'Parker';
name = 'Sophie'; // OK here
let name = 'Mike'; 
// SyntaxError: Identifier 'name' has already been declared
```
### compare to var
Scope
```js
function letscope {
    // i is *not* visible out here
    for (let i=0; i<10; i++){
        // i is visible only in the scope
    }
    // i is *not* visible out here
}
function varscope() {
    // i *is* visible out here
    for (var i=0; i<10; i++){
        // i is visible to the whole function
    }
    // i *is* visible out here
}
```
Redeclare
```js
let weight = 58;
let weight = 666; // SyntaxError
var money = 10000;
var money = 777777777; // It's OK
```
Global
```js
let nickname = 'hottie';  // globally scoped
var name = 'Parker'; // globally scoped

console.log(window.nickname); // undefined
console.log(window.name); // 'Pakrer'
```
|                      | let          | var                 |
| -------------------- | ------------ | ------------------- |
| variable             | block scope  | function scope      |
| redeclaration        | SyntaxError  | No problem          |
| global window object | not be added | added as properties |
## constant -> use const
- Enable protection for variables that must remain the same.
- Could improve performance.
- block-scoped
```js
const pi = 3.14;
pi = 15; // TypeError: Assignment to constant variable.
```
## [Note] const in array or object
```js
const arr = ['Parker', 'is'];
console.log(arr); // ['Parker', 'is']

arr.push('handsome!');
console.log(arr); // ['Parker', 'is', 'handsome!']
```
#### We won't get any error here.
#### Because in JS, array and object are reference type.
#### We didn't point this constant to something else, it still refers to the same memory location.
```js
const obj = {
    name: 'Teemo'
}
console.log(obj); // {name: 'Teemo'}

obj.skill = 'taunting';
console.log(obj); // {name: 'Teemo', skill: 'taunting'}
```

### If you use **object literal** to modify the contents of an object, then it's equivalent to creating a new object.
#### That is, it will save the object to another memory location, meaning this constant value has changed.
#### In the case below, the wrong message will appear (the array is the same)
```js
const obj = {
    name: 'Teemo'
}
console.log(obj); // {name: 'Teemo'}

obj = {
    name: 'Galen'
}
// TypeError: Assignment to constant variable.

const arr = [2, 4, 6];
console.log(arr); // [2, 4, 6]

arr = [1, 3, 5];
// TypeError: Assignment to constant variable.
```
### Conclution
Use let. Don't use var.