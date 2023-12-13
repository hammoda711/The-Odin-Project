# js notes on odin foundation #2

### string:

-All string methods return a new string. They **don't modify** the original string.

-A string can be converted to an array with the `split()` method:

-you can concatenate strings using `${ }` ,don't forget backtick ````

```js
const name = 'Chris';
const greeting = `Hello, ${name}`;
console.log(greeting); // "Hello, Chris" 
------------------------------------------------
const one = 'Hello, ';
const two = 'how are you?';
const joined = `${one}${two}`;
console.log(joined); // "Hello, how are you?"
```

------------------------

#### strings WARNING !!

-JavaScript uses the **+** operator for both **addition** and **concatenation**.

Numbers are added. Strings are concatenated.

-The JavaScript interpreter works from left to right.

```js
let x = 10;
let y = 20;
let z = "30";
let result = x + y + z; //3030   addition then concatenation
```

```js
let x = 10;
let y = 20;
let z = "30";
let result = z + x + y; //302010   concatination 
```

-JavaScript will try to convert strings to numbers in <u>all numeric operations</u> **except +**:

```js
let x = "100";
let y = "10";
let z = x / y;  //10
```

-for + operator: will **not convert** string into numbers

```js
let x = "100";
let y = "10";
let z = x + y; //10010
```

------------------------------------

### logiacal operator:

OR operator :

ex1:

```js
alert( 1 || 0 ); // 1 (1 is truthy)

alert( null || 1 ); // 1 (1 is the first truthy value)
alert( null || 0 || 1 ); // 1 (the first truthy value)

alert( undefined || null || 0 ); // 0 (all falsy, returns the last value)
```

ex2:

```js
let firstName = "";
let lastName = "";
let nickName = "SuperCoder";

alert( firstName || lastName || nickName || "Anonymous");// SuperCoder 

alert( firstName || lastName ||  "Anonymous"); // Anonymous 
       //all values are falsy, return the last value
```

-------------

AND operator:

```js
// if the first operand is truthy,
// AND returns the second operand:
alert( 1 && 0 ); // 0
alert( 1 && 5 ); // 5

//if the both are truthy, 
// AND will return the second.
alert( 3 && 2 );//2

// if the first operand is falsy,
// AND returns it. The second operand is ignored
alert( null && 5 ); // null
alert( 0 && "no matter what" ); // 0
```

----------------------------

example on logiacal operators:

```js
// Runs.
// The result of -1 || 0 = -1, truthy
if (-1 || 0) alert( 'first' );

// Doesn't run
// -1 && 0 = 0, falsy
if (-1 && 0) alert( 'second' );

// Executes
// Operator && has a higher precedence than ||
// so -1 && 1 executes first, giving us the chain:
// null || -1 && 1  ->  null || 1  ->  1
if (null || -1 && 1) alert( 'third' );
```

---------------------------

### condition:

#### notes on if

-in if condition, you can use one word insteed of expression using operators:

```js
let shoppingDone = false;
let childsAllowance;

if (shoppingDone) { // don't need to explicitly specify '=== true'
  childsAllowance = 10;
} else {
  childsAllowance = 5;
```

---

#### notes on switch:

Switch cases use **strict** comparison (===), The values must be of the **same type** to match.

```js
let x = "0";
switch (x) {
  case 0:
    text = "Off";
    break;
  case 1:
    text = "On";
    break;
  default:
    text = "No value found";
```

---

#### Ternary operator

-there is a way of condition called **Ternary operator** :

-`( condition ) ? run this code : run this code instead`

ex1

```js
let greeting = ( isBirthday ) ? 'Happy birthday' : 'Good morning';
```

ex2

```js
function getFee(isMember) {
  return (isMember ? '$2.00' : '$10.00');
}

console.log(getFee(true));
// expected output: "$2.00"

console.log(getFee(false));
// expected output: "$10.00"
```

ex3

```js
function example(…) {
    return condition1 ? value1
         : condition2 ? value2
         : condition3 ? value3
         : value4;
}
```

```js
let x = "true";
let y = "false";
let z= "true";
function greeting(i){
  return  x  ? "x"+i
         :y ? "y"          
         :z;
}

console.log(greeting(3)); //x3
```

------------------------------------------

### nullish coalescing operator:

The result of `a ?? b` is:

- if `a` is defined, then `a`,
- if `a` isn’t defined, then `b`.

```js
let user;

alert(user ?? "Anonymous"); // Anonymous (user not defined) 

------------------------------

let user = "john";

alert(user ?? "Anonymous"); // joun 
```

note: The OR `||` operator can be used in the same way as `??`

**WARNING:**

-due to safety reasons, JavaScript forbids using `??` together with `&&` and `||` operators, unless the precedence `()` 

```js
let x = 1 && 2 ?? 3; // Syntax error
```

```js
let x = (1 && 2) ?? 3; // Works

alert(x); // 2
```
