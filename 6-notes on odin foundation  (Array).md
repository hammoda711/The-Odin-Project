# js notes on odin foundation #5

## Array:

-Syntax: 

`const *array_name* = [*item1*, *item2*, ...];`

`const cars = new Array("Saab", "Volvo", "BMW");` 

**warning!!!**

no need to use `new Array()`

-The `typeof` operator in JavaScript returns "**object**" for arrays.

But, JavaScript arrays<u> are best described as arrays.</u>

-Array elements are accessed using their **index number**:

--------------------

### Array Const:

**-important!!!!! arrays is not constant** 

=-It is a common practice to declare arrays with the const keyword.

-The keyword `const` is a little misleading.

It does NOT define a constant array. It defines a **constant reference** to an array.

Because of this, we <u>can still change </u>the elements of a constant array.

****

-An **array** declared with `const` <u>cannot </u>be reassigned, but **elemnts** <u>can be reassigned</u> 

ex:

```js
const cars = ["Saab", "Volvo", "BMW"];
cars = ["Toyota", "Volvo", "Audi"];    // ERROR 


// You can create a constant array:
const cars = ["Saab", "Volvo", "BMW"];

// You can change an element:
cars[0] = "Toyota";

// You can add an element:
cars.push("Audi");
```

JavaScript `const` variables must be assigned a value when they are declared:

Meaning: An arrays declared with `const` <u>must be initialized </u>when it is declared.

Using `const` <u>without </u>initializing the array is a <u>syntax error</u>,

```js
const cars;
cars = ["Saab", "Volvo", "BMW"]; //error
```

-An array declared with `const` has **Block Scope**.

An array declared in a block is not the same as an array declared outside the block

```js
const cars = ["Saab", "Volvo", "BMW"];
// Here cars[0] is "Saab"
{
  const cars = ["Toyota", "Volvo", "BMW"]; //block scope
  // Here cars[0] is "Toyota"
}
// Here cars[0] is "Saab"
```

------------------------

### Array with var

-in contrast, Arrays declared with `var` can be initialized at any time.

You can even use the array before it is declared (**hoisting**):

```js
cars = ["Saab", "Volvo", "BMW"];
var cars;
```

 

-array declared with `var` does <u>not </u>have block scope:

```js
var cars = ["Saab", "Volvo", "BMW"];  
// Here cars[0] is "Saab"  
{  
  var cars = ["Toyota", "Volvo", "BMW"];  
   cars[0]; // "Toyota"  
}  
 cars[0];  // **"Toyota"**
```

so, Redeclaring an array declared with `var` is allowed anywhere in a program.

**important!!!!!! declaring a const array after declaring this arrray by( var or const) <u> is not allawed</u>** :

```js
var cars = ["Volvo", "BMW"];     // Allowed
const cars = ["Volvo", "BMW"];   // Not allowed errooooooor
{
  var cars = ["Volvo", "BMW"];   // Allowed

}
```

-----------------------

### Array with new Array()

it has the same results but There is no need to use `new Array()`.

For simplicity, readability and execution speed, use the array literal method.

------------------

### arrays vs. objects

Arrays use **numbers** to access its "elements". In this example,

```js
const person = ["John", "Doe", 46];

person[0]       //returns John
```

Objects use **names** to access its "members".  In this example,

```js
const person = {firstName:"John", lastName:"Doe", age:46};

person.firstName  // returns John
```

---------------------------------------

### Associative Arrays(warning!!!)

Arrays with named indexes are called associative arrays (or **hashes**).

JavaScript **does not support** arrays with named indexes.

In JavaScript, **arrays** always use **numbered indexes**.

```js
const person = [];

person[0] = "John"; // support it

person["first name"]= "john" // doesnot suppport it
```

----------------------

### usnig arrrays

-last Array elemnt:

```js
const fruits = ["Banana", "Orange", "Apple", "Mango"];
let fruit = fruits[fruits.length - 1];
```

---------------------

## adding element to an array

- push()

- unshift()

- splice()

-------------

### push()

using `push()` methods , `using length` word,

```js
const fruits = ["Banana", "Orange", "Apple"];
fruits.push("Lemon");  // Adds a new element (Lemon) to fruits

//or 
fruits[fruits.length] = "Lemon";  // Adds "Lemon" to fruits
```

**warning !!!!!!** 

Adding elements with high indexes can create undefined "holes" in an array:

```js
const fruits = ["Banana", "Orange", "Apple"];  
fruits[6] = "Lemon"; 
// Creates undefined "holes" // out: undefined untill find the index
```

-----------------

### push() vs. unshift()

The little difference is that:

- **unshift()** method adds the element <u>at 0 index</u> and all the values get shifted by 1 by ultimately returning the length of the array. 

-The **push()** method returns the last element adding a new elemen<u>t from the last index.</u>

------------------------------

### splice()

The `splice()` method can be used to add new items to an array:

```js
const fruits = ["Banana", "Orange", "Apple", "Mango"];  
fruits.splice(2, 0, "Lemon", "Kiwi");
```

- The first parameter (2) defines the position **where** new elements should be **added** (spliced in).

- The second parameter (0) defines **how many** elements should be **removed**.

- The rest of the parameters ("Lemon" , "Kiwi") define the new elements to be **added**

- The `splice()` method returns an array with the deleted items

--------------------------------

## remove elemnts from an array

#### Warning !

- shift()

- pop()

- splice()

-The `shift()` method <u>removes the first array element </u> and "shifts" all other elements to a lower index.`shift()` return the deleted element and chanage the original array.

-The `pop()` method <u>removes the last element</u> from an array,`pop()`return the deleted element and chanage the original array 

-to use`splice()` for removing elements: 

```js
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(0, 1);
```

------------------------

### using delete()!!!!!!!!!!!!!

Array elements can be deleted using the JavaScript operator `delete`.

Using `delete` leaves `undefined` holes in the array.

Use `pop()` or `shift()`instead.

-------------------

### concatenation(merging):

The `concat()` method does not change the existing arrays. It always returns a <u>new array</u>.

The `concat()` method can take any number of array arguments:

The `concat()` method can also take strings as arguments:

```js
const fruits = ["Banana", "Orange", "Apple"];  
const x =["mm","das"];
const y = ["asf", "ashf"];
let z = fruits.concat(x, y,"ya rab");
console.log(z);
//['Banana', 'Orange', 'Apple', 'mm', 'das', 'asf', 'ashf', "ya rab"]
```

----------------

### slice()

-The `slice()` method slices out a piece of an array into a new array.

-The `slice()` method does not remove any elements from the source array.

```js
const fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];  
const citrus = fruits.slice(1); // Orange, Lemon, Apple, Mango
```

```js
const fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];  
const citrus = fruits.slice(3); //Apple,Mango

alert(fruits); //banana,Orange,Lemon,Apple,Mango
```

### note

-The `slice()` method can take two arguments like `slice(1, 3)`.

The method then selects elements from the start argument, and up to (but not including) the end argument.

```js
const fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
const citrus = fruits.slice(1, 3);// Orange,Lemon,Apple
             // return element which its index is 1,2,3
```
