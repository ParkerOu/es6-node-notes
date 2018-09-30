# Things must know before go ahead
## JS syntax is like C
```js
if (score >= 60){
    console.log('passed!');
} else {
    console.log('failed!');
}
```
## JS is **Dynamic typing**
Type checking is running at **runtime**
## JS is **Weak typing**
**Type can change** on runtime  
```js
seven = '7';
eleven = 11;
console.log(seven + eleven);
// output '711'
```
variable eleven type auto convert from int to string
## JS is **Asynchronous**
You can’t just call one function after another and hope they execute in the right order.
```js
function first(){
  // Simulate a code delay
  setTimeout( function(){
    console.log(1);
  }, 500 );
}
function second(){
  console.log(2);
}
first();
second();
// output: 2
// output: 1
```