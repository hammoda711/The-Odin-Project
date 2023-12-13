# js notes on odin foundation #1

## all the following is important:

### naming in js:

-Naming Things: Names for functions and variables should be descriptive. Always use camelCase. 

-To keep things consistent and easy to read, <u>**variables**</u> should always begin with a <u>noun </u>or an <u>adjective </u>(that is, a noun phrase)

-**<u>functions </u>** should always begin with a <u>verb </u>,

-It is ok to use **single characters** as **variable** names in the <u>context of a loop </u>or a <u>callback function,</u> but not elsewhere.

-----------------------------------------

### comments:

[Self Documenting Code (c2.com)](http://wiki.c2.com/?SelfDocumentingCode)

a decumentry for commints and advices in best practise

--------------------------

#### Uppercase constants

There is a widespread practice to use constants as aliases for difficult-to-remember values that are known prior to execution.

```js
const COLOR_RED = "#F00";
const COLOR_GREEN = "#0F0";
const COLOR_BLUE = "#00F";
const COLOR_ORANGE = "#FF7F00";

// ...when we need to pick a color
let color = COLOR_ORANGE;
alert(color); // #FF7F00
```

---------------------------

#### precedence

[JavaScript Arithmetic (w3schools.com)](https://www.w3schools.com/js/js_arithmetic.asp)

--------------------------

#### Integer Precision(Approximation)

Integers (numbers without a period or exponent notation) are accurate up to **15** digits

```js
let x = 999999999999999;   // x will be 999999999999999
let y = 9999999999999999;  // y will be 10000000000000000
```

-------------

-all math operations convert **empty strings**  " " and **spaces** \n , \t into 0

```js
x = " \t \n" - 2;   // -2
```

------------------

-`Infinity` (or `-Infinity`) is the value JavaScript will return if you calculate a number outside the largest possible number.

-Division by 0 (zero) also generates `Infinity`

--------------------------------

`==` compare values  
`===` compare data types
-except in object both == and === retutn false 
 because it compares the two refrences not the value or the datatype.

--------------------

#### numeric conversion

-the plus operator `+` applied to a single value, doesn’t do anything to numbers. But if the operand is **not a number**, the unary plus **converts it into a number.**

```js
let apples = "2";
let oranges = "3";

// both values converted to numbers before the binary plus
alert( +apples + +oranges ); // 5

// the longer variant
// alert( Number(apples) + Number(oranges) ); // 5
```

-----------------------------

#### note that:

```js
let n = 2;
n += 5; // now n = 7 (same as n = n + 5)
n *= 2; // now n = 14 (same as n = n * 2 let n = 2;
-----------------------------------------------------------------------
let n = 2;
n *= 3 + 5;  // 16  (right part evaluated first, same as n *= 8
             // which equal to n = n *8))
```

-------------------------

#### increment and decrement

-Increment/decrement can only be applied to variables. Trying to use it on a value like `5++` will give an error.

##### pre increment

```js
let counter = 1;
let a = ++counter; // work on one line
                  //general effect

alert(a); // 2
```

##### post increment

```js
let counter = 1;
let a = counter++; // work on more than one line,
                  // need to display the variable 'counter' 
                 // to get the value after increment
                //special effect on counter 

alert(a); // 1 the value before increment
```

--------------------------------

#### notes:

```js
y = true + false ; // 1 + 0 = 1
```

```js
"4px" - 2 = NaN
```

------------------------------

#### difference between ***null*** and ***undefined***

|                              | **null**                                                                                                                                                                                                                   | undefined                                                                                                     |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| for value in math operations | = 0 <br>`x = null + 1;  // 0 + 1 = 1`                                                                                                                                                                                      | `y = undefined + 1; // NaN`                                                                                   |
| for variable                 | not declared                                                                                                                                                                                                               | declared but not assigned<br>                                                                                 |
|                              | alert( null > 0 ); // false<br/>alert( null == 0 ); //  false<br/>alert( null === 0 ); //  false<br>alert( null >= 0 ); // **true** <br><br>-beacause in  js  equality check == and comparisons > < >= <= work differently | alert( undefined > 0 ); // false <br/>alert( undefined < 0 ); // false <br/>alert( undefined == 0 ); // false |

-----------------------

#### difference between ***let*** and ***var***

let: block scope 

var: global scope

------------------------------------------------------------
