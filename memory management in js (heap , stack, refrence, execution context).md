## memory managment in js

### point to be known:

- **JavaScript engine** uses a **call stack** to manage **execution contexts.**
- The **call stack** use the **stack data structure** that works based on the **LIFO** (last-in first-out) principle.

----------------------

### execution context (global , function)

***very important !!!!!!!!!!!!!!*** [Understanding JavaScript Execution Context By Examples](https://www.javascripttutorial.net/javascript-execution-context/)

---

### call stack

***very important !!!!!!!!!!!!!!*** [JavaScript Call Stack](https://www.javascripttutorial.net/javascript-call-stack/)

-very  important !!!!!!!!! [JavaScript's Memory Management Explained (felixgerschau.com)](https://felixgerschau.com/javascript-memory-management/#references-in-javascript)

##### **stack over flow error:**

-The call stack has a **fixed size**, depending on the implementation of the host environment, either the web browser or Node.js.

If the number of the execution contexts exceeds the size of the stack, a stack overflow error will occur.

For example, when you execute a [recursive function](https://www.javascripttutorial.net/javascript-recursive-function/) that has **no exit condition**, the JavaScript engine will issue a stack overflow error:

```js
function fn() {
    fn();
}

fn(); // stack overflow
```

---

### memory life cycle:

**Memory allocation**: JavaScript takes over this task: it allocates the memory that will be needed for the object we created.

**Memory usage**: This is what we explicitly write in the code: reading and writing to memory is nothing more than reading and writing to a variable.

**Freeing up memory:** This step is also performed by the JavaScript engine: immediately after freeing up the memory, you can use it for other purposes.

--------------------

### different between stack and heap in js

very important !!!!!!!!

[JavaScript stack size | Better world by better software (glebbahmutov.com)](https://glebbahmutov.com/blog/javascript-stack-size/)

| stack                              | heap                                                                                |
| ---------------------------------- | ----------------------------------------------------------------------------------- |
| Primitive values and references    | Objects and functions                                                               |
| Size is known at compile time      | Size is known at run time                                                           |
| Allocates a fixed amount of memory | No limit per object                                                                 |
| static memory allocation           | dynamic memory allocation                                                           |
|                                    | The memory of the heap is not ordered<br> , so it uses the refrence from the stack. |
| **compile time memory allocation** | **runtime memory allocation**                                                       |

![Stack heap pointers explained](https://felixgerschau.com/static/b452488bd7eeac0405c48f164da6280d/5a190/stack-heap-pointers.png)

----------------------------

### difference between object and refrence :

-You can think of references as addresses and the objects in the heap as houses that these addresses belong to.

-very important!!!!!  https://felixgerschau.com/javascript-memory-management/#references-in-javascript

-------------------------

### defrence between compile time and run time:

<img title="Rendered by QuickLaTeX.com" src="https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-25c5794ab97de69a698576bf136da63a_l3.svg" alt="Rendered by QuickLaTeX.com" data-align="inline">

-image link https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-25c5794ab97de69a698576bf136da63a_l3.svg

--------------------

### difference between compile, execution, load time:

### <img title="" src="https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-6ddc649141d94a08ca3fff5243a9d4fd_l3.svg" alt="Rendered by QuickLaTeX.com" width="615">

-image link https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-6ddc649141d94a08ca3fff5243a9d4fd_l3.svg

---------------

### Asynchronous JavaScript:

-JavaScript is the **single-threaded** programming language. This means that the JavaScript engine has **only one call stack**. Therefore, it only can **do one thing at a time**.

-**synchronous** means the JavaScript engine executes code<u> from top to bottom</u>, <u>line by line</u>. 

-**Asynchronous** means the JavaScript engine can execute other tasks while **waiting** for another task to complete.

-**blocking function**: function that takes a long time to complete. Technically, a blocking function blocks all the interactions on the webpage, such as mouse click.
