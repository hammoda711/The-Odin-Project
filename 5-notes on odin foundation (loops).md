# loops

## while, do .. while

```js
let i = 0;
while (i < 3) { // when i becomes 0, the condition becomes falsy, and the loop stops
  alert( i );
  i++;
}
//output 
//0
//1
//2
```

```js
let i = 0;
do {
  alert( i );
  i++;
} while (i < 3);

//output 
//0
//1
//2
```

--------------

## for loop()

### Inline variable declaration

Here, the “counter” variable `i` is declared right **in the loop**. This is called an “inline” variable declaration. Such variables are visible only inside the loop.

```js
for (let i = 0; i < 3; i++) {
  alert(i); // 0, 1, 2
}
alert(i); // error, no such variable
```

Instead of defining a variable, we could use an existing one:

```js
let i = 0;

for (i = 0; i < 3; i++) { // use an existing variable
  alert(i); // 0, 1, 2
}

alert(i); // 3, visible, because declared outside of the loop
```

**note:**

-you can skip any part of the for loop:

```js
let i = 0; // we have i already declared and assigned

for (; i < 3; i++) { // no need for "begin"
  alert( i ); // 0, 1, 2
}
```

```js
let i = 0;

for (; i < 3;) {
  alert( i++ );
}
```

--------------

### break, continue
