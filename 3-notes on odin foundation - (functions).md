# js notes on odin foundation #3 (functions)

### functions:

 function names should be concise and descriptive.

#### parameters:

-**Parameters** are sometimes called arguments, properties, or even attributes.

-there are four cases for parameters: 

1. functions that donot need parameters ex: `Math.random()`

2. function that necassary need a parameter ex: `replace()`

3. optional parameters: that if you donot give the function wil use default parameters 
   
   ex: `join()` has use comma `,` as  defult parameter 

4. default parameters: 
   
   ```js
   function hello(name='Chris') {
    console.log(`Hello ${name}!`);
   }
   
   hello('Ari'); // Hello Ari!
   hello();      // Hello Chris!  
   ```

note: the parameter can be another **function!!!!!!!**:

```js
function showMessage(from, text = anotherFunction()) {
  // anotherFunction() only executed if no text given
  // its result becomes the value of text
}
```

note: if the parameter is not in the (), you must declare the variable, if you want to use it (the parameter), 

```js
function favoriteAnimal(animal) {
  console.log(animal + " is my favorite animal!")
}

favoriteAnimal('Goat') 
--------------------------------------------------------
function favoriteAnimal() {
let animal= "zibra";       // you have to declare a variable
                          // to use it in the print and give an argument 
  console.log(animal + " is my favorite animal!")
}

favoriteAnimal('Goat')   // argument 
```

**note**: 

-A parameter is the variable listed inside the parentheses in the function declaration (it’s a declaration time term)

-An argument is the value that is passed to the function when it is called (it’s a call time term).

---------------

#### function types :

1- **anonymous function** :it has no name. You'll often see anonymous functions <u>when a function expects to receive another function as a parameter.</u>

```js
function(){
    alert(" hi")
}
```

ex:  `function(event)` is the anonymous func:

```js
textBox.addEventListener('keydown', function(event) {
  console.log(`You pressed "${event.key}".`);
});
```

2- **arrow functions**:  Instead of `function(event)`, you write `(event) =>`

```js
textBox.addEventListener('keydown', (event) => {
  console.log(`You pressed "${event.key}".`);
});
```

-you can ignore the {} and () around event and also ignore the `return` statment

exeplanation in this link,  [Arrow functions](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Functions#arrow_functions "Permalink to Arrow functions")

-more  features of arrow functions : https://javascript.info/arrow-functions

1. Do not have `this`

2. Do not have `arguments`

3. Can’t be called with `new`

4. They also don’t have `super`

---------------------

### Function scope and conflicts:

-global scope is not preferred because of security and organization. 

for example if you call **two** external JavaScript files, and both of them have a variable and a function defined that use the same name, the first will work and the second will ignored (and has an error).  [Function scope and conflicts](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Functions#function_scope_and_conflicts "Permalink to Function scope and conflicts")

--------------------------------

### function inside function

**note**: you can not make a big function include subfunctions <u>without making the big function including  the variables in the subfunctions (because of scope ) </u>

ex:

```js
function myBigFunction() {
  const myValue = 1; //you have to do that!!!!!!!

  subFunction1(myValue);
  subFunction2(myValue);
  subFunction3(myValue);
}

function subFunction1(value) {
  console.log(value);
}

function subFunction2(value) {
  console.log(value);
}

function subFunction3(value) {
  console.log(value);
}
```

**Note:** The same scoping rules **do not** apply to loop (e.g. `for() { ... }`) and conditional blocks (e.g. `if() { ... }`) 

-----------------

### return values:

-A function with an empty `return` or without it, returns `undefined`

If a function does not return a value, it is the same as if it returns `undefined`:

```js
function doNothing() { /* empty */ }

alert( doNothing() === undefined ); // true
```

```js
function doNothing() {
  return;
}

alert( doNothing() === undefined ); // true
```

**note**: it is preferred to use return with a values in the same line or use () for multiine:

-----------------------

### passing a function as:

-function can be passed as a **value**, to a variable and <u>this variable becomes a function </u>with the same job :

```js
 function sayHi() {   // (1) create
  alert( "Hello" );
}

let func = sayHi;    // (2) copy

func(); // Hello     // (3) run the copy (it works)!
sayHi(); // Hello    //     this still works too (why wouldn't it)
```

```js
//an other way to declare function:
--------------------------------------------------------------


let sayHi() = function(){   

 alert( "Hello") 
};        // take care!!!! there is  ;  after };
```

-functions can be passed as an **argument**:

```js
function ask(question, yes, no) {
  if (confirm(question)) yes()
  else no();
}

function showOk() {
  alert( You agreed." );
}

function showCancel() {
  alert( "You canceled the execution." );
}

// usage: functions showOk, showCancel are passed as arguments to ask
ask("Do you agree?", showOk, showCancel);
```

-**The arguments `showOk` and `showCancel` of `ask` are called *callback functions* or just *callbacks*.**

-the same code with function exepression using anonymous functions:

```js
function ask(question, yes, no) {
 if (confirm(question)) yes()
 else no();
}

ask(
 "Do you agree?",
 function() { alert("You agreed."); },
 function() { alert("You canceled the execution."); }
);
```

-------------------------

### function decalration vs function expression:

|          | declaration                                               | exepression                                   |
| -------- | --------------------------------------------------------- | --------------------------------------------- |
| sybtax   | `function() { alert("Greetings!"); };`                    | `welcome = function() {alert("Greetings!")};` |
| hoisting | yes (declaration after callnig work normally)             | no (error)                                    |
| scope    | only inside its block scope<br>ex: conditional declaraion | outside block scope (usnig global variables)  |
| notes    | more eye catching                                         |                                               |

here a link for more info [Function Expression vs Function Declaration](https://javascript.info/function-expressions#function-expression-vs-function-declaration)

---------------------------
