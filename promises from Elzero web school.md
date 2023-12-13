# promises from Elzero web school

**promise:** is an object that express the state of the asyncronuous function (failure or success).

-promise use function callback.

-promise hase 3 states(and only one state can be done for one promice)

1. fulfilled (success)

2. rejected

3. pending

-promise has an execution function that contain the **(resolve and reject)** handelers

which responsible for the success or the failure of the promice.

-promise use the `.then()`  to access the data of resolve and rejected snd it also responsible for chaining promises.

-`.then(parameter1 , parameter 2) `  two parameters are required!!!!!!

```javascript
const myPromise = new Promise((resolve, reject) => {
  // console.log("Welcome To My First Promise");
  /*    Asynchronous Operation    Fulfilled => resolve    Rejected => reject  */

  let connect = true;
  if (connect) {
    resolve("Connection Established");
  } else {
    reject(Error("Connection Failed"));
  }
}).then(  //chaining
  (resolved) => console.log(resolved),
  (rejected) => console.log(rejected)
);

console.log(typeof myPromise);//return object
//----------------------------------------------------------------------
// Another Syntax

const theResolved = (resolved) => console.log(resolved);
const therejected = (rejected) => console.log(rejected);

myPromise.then(theResolved, therejected);
//--------------------------------------------------------------------


//to catech the failures use catch for failures 
//or use then to cath them 


myPromise.then(null, (rejected) => console.log(rejected));
// access only the rejected state (failure)
//or
myPromise.catch((rejected) => console.log(rejected));
```

--------------
