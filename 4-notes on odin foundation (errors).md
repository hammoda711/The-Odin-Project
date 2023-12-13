## js notes on odin foundation #4

### errors:

### error structure:

![Screen Shot 2021-05-17 at 12 15 06 PM](https://cdn.statically.io/gh/TheOdinProject/curriculum/284f0cdc998be7e4751e29e8458323ad5d320303/foundations/javascript_basics/understanding_errors/imgs/01.png)

-`error type`  :  `what exactly happened`  at  `file.js`  :  `line num`  :  `column num` 

-----------

### common error types:s

##### **(1) syntax error**:

A syntax error occurs when the code you are trying to run is not written correctly, 

```js
console.log "Hello World!" // console.log() suntax error
```

###### warning!!!!!!

**Declaring twice triggers an error:**

A variable should be declared only once.

A repeated declaration of the same variable is an error:

```js
let message = "This";
// repeated 'let' leads to an error
let message = "That"; 
// SyntaxError:'message' has already been declared`
```

So, we should declare a variable once and then refer to it without `let`.

##### (2)Refernce error:

A ReferenceError is thrown when one refers to a variable that is not declared and/or initialized within the current scope, it has been spelt incorrectly.

```js
const a = "Hello"
const b = "World"

console.log(c) //reference error 
```

##### (3)syntax error:

 a `TypeError` may be thrown when :

- an operand or argument passed to a function is incompatible with the type expected by that operator or function;

- or when attempting to modify a value that cannot be changed;

- or when attempting to use a value in an inappropriate way.

```js
const str1 = "Hello";
const str2 = "World!";
const message = str1.push(str2);
//we get a TypeError with a message that str1.push is not a function.
//it means that  .push() is not a String method, it’s an Array method.
```

-----------------
