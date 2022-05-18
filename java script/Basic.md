```javascript
document.getElementById("demo").style.display = "none";
document.getElementById("demo").style.display = "block";
document.getElementById("demo").style.fontSize = "35px";
document.getElementById("demo").innerHTML = "Hello JavaScript";

```

- **JavaScript Output::** 

  - innerHTML

  - document.write()

  - window.alert()  // same as alert()

  - console.log()

  - window.print() 

    - it will give you option to save or print your page in your local system.

    - ```javascript
      <button onclick="window.print()">Print this page</button>
      ```

- Java Script is case sensitive.

- A variable declared without a value will have the value `undefined`.

- Remember that JavaScript identifiers (names) must begin with:

  - A letter (A-Z or a-z)
  - A dollar sign ($)
  - Or an underscore (_)

- ***Let::***

  - Variables defined with `let` cannot be Redeclared but reassigned.

  - Variables defined with `let` must be Declared before use.

    ```javascript
    console.log(a); // we are using before declaring it.
    let a=10 // 
    ```
  
    ```javascript
    let a;
    console.log(a); // undefined no error.s
    ```
  
  - Variables defined with `let` have Block Scope.
  
  - ```javascript
    let x = "John Doe"
    let x = 0;
    // SyntaxError: 'x' has already been declared
    
    let x = "John Doe"
    x = 0; // no issue because it is reassigned.
    
    With var you can:
    
    var x = "John Doe";
    var x = 0;
    ```
    
    
    
    ```javascript
    {
      let x = 2;
    }
    // x can NOT be used here
    
    {
      var x = 2;
    }
    // x CAN be used here
    ```
    
  - Redeclaring a variable **inside a block** will also redeclare the variable outside the block:
  
    ```javascript
    var x = 10;
    // Here x is 10
    
    {
    var x = 2;
    // Here x is 2
    }
    
    // Here x is 2
    ```
  
  - Redeclaring a variable inside a block will not redeclare the variable outside the block:
  
    ```javascript
    let x = 10;
    // Here x is 10
    
    {
    let x = 2;
    // Here x is 2
    }
    
    // Here x is 10
    ```
  
  - With `let`, redeclaring a variable in the same block is NOT allowed:
  
    ```javascript
    var x = 2;    // Allowed
    let x = 3;    // Not allowed
    
    {
    let x = 2;    // Allowed
    let x = 3     // Not allowed
    }
    
    {
    let x = 2;    // Allowed
    var x = 3     // Not allowed
    }
    ```
  
    ```javascript
    let a=10;
    {
    var a=20; // not allowed.
    }
    ```
  
    ```javascript
    {
      let a=10;
    }
    {
    var a=20; // Allowed.
    }
    ```
  
    ```javascript
    var a=10;
    {
    let a=20; // allowed.
    }
    ```
  
    
  
    ```javascript
    let x = 2;    // Allowed
    
    {
    let x = 3;    // Allowed
    }
    
    {
    let x = 4;    // Allowed
    }
    ```
  
  - ## Let Hoisting
  
    - Variables defined with `var` are **hoisted** to the top and can be initialized at any time.
  
      ```javascript
      carName = "Volvo";
      var carName;
      ```
  
      ```javascript
      let a; // allowed;--|| Here value will be undefined.
      const a; // not allowed.
      ```
  
    - Using a `let` variable before it is declared will result in a `ReferenceError`:
  
      ```javascript
      carName = "Saab";
      let carName = "Volvo";
      ```
  
  - ***Const::***
  
    - Variables defined with `const` cannot be Redeclared.
  
    - Variables defined with `const` cannot be Reassigned.
  
    - Variables defined with `const` have Block Scope.
  
    - Will have to assign value at the time of declaration.
  
    - ```javascript
      const PI = 3.141592653589793;
      PI = 3.14;      // This will give an error
      PI = PI + 10;   // This will also give an error
      ```
  
    - JavaScript `const` variables must be assigned a value when they are declared:
  
      ```javascript
      const PI = 3.14159265359; // correct
      
      const PI;  // incorrect
      PI = 3.14159265359;
      ```
  
    - **Const** does not define a constant value. It defines a constant reference to a value.
  
    - You can change the elements of a constant array:
  
      ```javascript
      // You can create a constant array:
      const cars = ["Saab", "Volvo", "BMW"];
      
      // You can change an element:
      cars[0] = "Toyota";
      
      // You can add an element:
      cars.push("Audi");
      ```
  
      
  
      ```javascript
      const cars = ["Saab", "Volvo", "BMW"];
      
      cars = ["Toyota", "Volvo", "Audi"];    // ERROR
      ```
  
    - Declaring a variable with `const` is similar to `let` when it comes to **Block Scope**.
  
    - ```javascript
      var x = 2;     // Allowed
      const x = 2;   // Not allowed
      
      {
      let x = 2;     // Allowed
      const x = 2;   // Not allowed
      }
      
      {
      const x = 2;   // Allowed
      const x = 2;   // Not allowed
      }
      ```
  
      
      
      ```javascript
      const x = 2;     // Allowed
      x = 2;           // Not allowed
      var x = 2;       // Not allowed
      let x = 2;       // Not allowed
      const x = 2;     // Not allowed
      
      {
        const x = 2;   // Allowed
        x = 2;         // Not allowed
        var x = 2;     // Not allowed
        let x = 2;     // Not allowed
        const x = 2;   // Not allowed
      }
      ```
      
      
      
      ```javascript
      const x = 2;       // Allowed
      
      {
        const x = 3;   // Allowed
      }
      
      {
        const x = 4;   // Allowed
      }
      ```
      
    - Variables declared via let and const are hoisted as well. However, unlike var and function, they are not initialized and accessing them before the declaration will result in a ReferenceError exception. The variable is in a "temporal dead zone" from the start of the block until the declaration is processed.
  
      ```javascript
      x; // undefined
      y; // Reference error: y is not defined
       
      var x = 'local';
      let y = 'local';
      ```
  
  - ***Hoisting::***
  
    - Hoisting is JavaScript's default behaviour of moving **declarations** to the top.
  
    - Only **declaration** moves at the top not **assignment**
  
      ```javascript
      x = 5; // Assign 5 to x
      
      elem = document.getElementById("demo"); // Find an element
      elem.innerHTML = x;                     // Display x in the element
      
      var x; // Declare x
      ```
  
  - Variables defined with `let` and `const` are hoisted to the top of the block, but not *initialized*.
  
    - In the below example value of the y will be printed as **undefined.**  
  
    - ```javascript
      var x = 5; // Initialize x
      
      elem = document.getElementById("demo"); // Find an element
      elem.innerHTML = x + " " + y;           // Display x and y
      
      var y = 7; // Initialize y
      ```
  
    - In hoisting var is provided a value as undefined but let and const does not.
  
    - ```javascript
      carName = "Volvo";
      let carName;
      This will result in a ReferenceError:
      ```
  
    - Using a `const` variable before it is declared, is a syntax errror, so the code will simply not run.
  
    - ```javascript
      carName = "Volvo";
      const carName;
      This code will not run.
      ```
  
  - ***"use strict";*** 
  
    - declare a variable or function before use.
  
      ```javascript
      "use strict";
      x = 3.14;       // This will cause an error because x is not declare
      ```
  
      
      
      ```javascript
      "use strict";
      myFunction();
      
      function myFunction() {
        y = 3.14;   // This will also cause an error because y is not declared
      }
      ```
  
  - **this()::**
  
    - In a method, `this` refers to the **owner object**.
  
    - Alone, `this` refers to the **global object**.
  
    - In a function, `this` refers to the **global object**.
  
    - In a function, in strict mode, `this` is `undefined`.
  
    - ```javascript
      # here this is pointing to person.
      const person = {
        firstName: "John",
        lastName : "Doe",
        id       : 5566,
        fullName : function() {
          return this.firstName + " " + this.lastName;
        }
      };
      ```
  
      
      
      ```javascript
      # here this is pointing to window
      let x = this;
      ```
      
      
      
      ```javascript
      # here this is pointing to window
      function myFunction() {
        return this;
      }
      ```
      
      
      
      ```javascript
      # here this is undefined
      "use strict";
      function myFunction() {
        return this;
      
      ```
  
  - ## JavaScript Class::
  
    - Use the keyword `class` to create a class.
    - Always add a method named `constructor()`:
  
    ```javascript
    class Car {
      constructor(name, year) {
        this.name = name;
        this.year = year;
      }
    }
    ```
  
  - ## The Constructor Method
  
    - It has to have the exact name "constructor"
  
    - It is executed automatically when a new object is created
  
    - It is used to initialize object properties
  
    - ```javascript
      class Car {
        constructor(name, year) {
          this.name = name;
          this.year = year;
        }
        age() {
          let date = new Date();
          return date.getFullYear() - this.year;
        }
      }
      
      let myCar = new Car("Ford", 2014);
      document.getElementById("demo").innerHTML =
      "My car is " + myCar.age() + " years old.";
      ```
  
  - JavaScript built-in function `JSON.parse()` to convert the string into a JavaScript object:
  
    
  
  - Arrow functions do not have their own `this`. They are not well suited for defining **object methods**.
  
  - Arrow functions are not hoisted. They must be defined **before** they are used.
  
- ## Function Rest Parameter::(...)

  - ```javascript
    function sum(...args) {
      let sum = 0;
      for (let arg of args) sum += arg;
      return sum;
    }
    
    let x = sum(4, 9, 16, 25, 29, 100, 66, 77);
    ```

- ## JavaScript Objects::

  - In JavaScript, almost "everything" is an object.

  - ```javascript
    const person = {
      firstName:"John",
      lastName:"Doe",
      age:50, 
      eyeColor:"blue"
    }
    
    const x = person;
    x.age = 10;      // Will change both x.age and person.age
    ```
    
  - Any JavaScript object can be stringified (converted to a string) with the JavaScript function `JSON.stringify()`:

  - ```javascript
    const person = {
      name: "John",
      age: 30,
      city: "New York"
    };
    
    let myString = JSON.stringify(person);
    ```

  - JSON.stringify will not stringify **functions.**

  - You have to convert functions to strings first:

  - ```javascript
    <p id="demo"></p>
    
    <script>
    const person = {
      name: "John",
      age: function () {return 30;}
    };
    person.age = person.age.toString();
    
    document.getElementById("demo").innerHTML = JSON.stringify(person);
    </script>
    # output
    {"name":"John","age":"function () {return 30;}"}
    ```

  - JSON.stringify can stringify arrays:

    ```javascript
    const arr = ["John", "Peter", "Sally", "Jane"];
    
    let myString = JSON.stringify(arr);
    ```

- you can **not** add a new property to an existing object constructor:

  ```javascript
  function Person(first, last, age, eye) {
    this.firstName = first;
    this.lastName = last;
    this.age = age;
    this.eyeColor = eye;
  }
  
  Person.nationality = "English"; # will give undefined if used by something.
  ```
  
- The JavaScript `prototype` property allows you to add new properties to object constructors:

  ```javascript
  function Person(first, last, age, eyecolor) {
    this.firstName = first;
    this.lastName = last;
    this.age = age;
    this.eyeColor = eyecolor;
  }
  
  Person.prototype.nationality = "English";
  
  Person.prototype.name = function() {
    return this.firstName + " " + this.lastName;
  };
  ```

- ## JS Functions::

  - The function below is actually an **anonymous function** (a function without a name).

    Functions stored in variables do not need function names. They are always invoked (called) using the variable name.

    ```javascript
    const x = function (a, b) {return a * b};
    let z = x(4, 3);
    ```

  - ## Function Hoisting

    ```javascript
    myFunction(5);
    
    function myFunction(y) {
      return y * y;
    }
    ```

  - Arrow functions are not hoisted. They must be defined **before** they are used.

  - ***call( )::***

    - The `call()` method is a predefined JavaScript method.

    - ```javascript
      const person = {
        fullName: function() {
          return this.firstName + " " + this.lastName;
        }
      }
      const person1 = {
        firstName:"John",
        lastName: "Doe"
      }
      // This will return "John Doe":
      person.fullName.call(person1); // this will sudden call that function.
      ```

    - ```javascript
      const person = {
        fullName: function(city, country) {
          return this.firstName + " " + this.lastName + "," + city + "," + country;
        }
      }
      
      const person1 = {
        firstName:"John",
        lastName: "Doe"
      }
      
      person.fullName.call(person1, "Oslo", "Norway");
      ```

  - ***apply()::***

    - The `apply()` method is similar to the `call()` method

    - The `call()` method takes arguments **separately** but The `apply()` method takes arguments as an **array**.

    - ```javascript
      const person = {
        fullName: function(city, country) {
          return this.firstName + " " + this.lastName + "," + city + "," + country;
        }
      }
      
      const person1 = {
        firstName:"John",
        lastName: "Doe"
      }
      
      person.fullName.apply(person1, ["Oslo", "Norway"]);
      ```

  - **bind( )::**

    ```javascript
    const person = {
      firstName:"John",
      lastName: "Doe",
      fullName: function () {
        return this.firstName + " " + this.lastName;
      }
    }
    
    const member = {
      firstName:"Hege",
      lastName: "Nilsen",
    }
    
    let fullName = person.fullName.bind(member);// bind never calls the function but it returns the function.
    ```

    ```javascript
    const person = {
      firstName:"John",
      lastName: "Doe",
      display: function () {
        let x = document.getElementById("demo");
        x.innerHTML = this.firstName + " " + this.lastName;
      }
    }
    
    setTimeout(person.display, 3000);// undefined undefined because person.display is a function which is now not related to any object
    setTimeout(person.display(), 3000); // John Doe because you are sudden calling a function 
    ```

    ```javascript
    function add(a, b) {
     return a + b;
    }
     
    console.log(add.call(null, 1, 2)); // 3
    console.log(add.apply(null, [1, 2])); // 3
    ```

    

  - ## JavaScript Closures::

    - The inner function inside a function always remembers the values of the function . this property is called as closure.

    - ```javascript
      function func(){
          let a=10;
          const f=function(){return a*a}
      }
      let val=func.f # here val is storing function
      console.log(val()) # calling function will give value of a*a
      # here val is remembring the value of a even after func eecution is done.
      ```
      
    - **Closure helpful in data hiding or encapsulation.**

      ```javascript
      function counter() {
        var count = 0;
        return function increment() {
          count++;
          console.log(count);
        };
      }
      
      var counter1 = counter();
      counter1(); //1
      counter1(); //2
      
      var counter2 = counter();
      counter2(); //1
      counter2(); //2
      counter2(); //3
      counter2(); //4
      ```

      

  - ## JS Classes::

    - Unlike functions, and other JavaScript declarations, class declarations are not hoisted.

    - That means that you must declare a class before you can use it:

    - ```javascript
      class Car {
        constructor(brand) {
          this.carname = brand;
        }
      }
      
      //Now you can use the class:
      let myCar = new Car("Ford")
      ```

- ## JavaScript Callbacks::

  - A callback is a function passed as an argument to another function

  - This technique allows a function to call another function

  - A callback function can run after another function has finished

  - ```javascript
    setTimeout(myFunction, 3000);
    ```

  - ```javascript
    function myDisplayer(some) {
      document.getElementById("demo").innerHTML = some;
    }
    
    function myCalculator(num1, num2, myCallback) {
      let sum = num1 + num2;
      myCallback(sum);
    }
    
    myCalculator(5, 5, myDisplayer);
    ```

  - callbacks really shine are in asynchronous functions, where one function has to wait for another function (like waiting for a file to load).

- ## Asynchronous JavaScript::

  - Functions running in parallel with other functions are called asynchronous.
  - A good example is JavaScript setTimeout()
  - 

- ## JavaScript Promises::

  ![image-20220220232454665](C:\Users\RAHUL AGARWAL\AppData\Roaming\Typora\typora-user-images\image-20220220232454665.png)

  - ```javascript
    let myPromise = new Promise(function(myResolve, myReject) {
    // "Producing Code" (May take some time)
    
      myResolve(); // when successful
      myReject();  // when error
    });
    
    // "Consuming Code" (Must wait for a fulfilled Promise)
    myPromise.then(
      function(value) { /* code if successful */ },// first function in then will be resolve
      function(error) { /* code if some error */ } // second function will be error.
    );
    ```

  - **There can be only a single result or an error**

    The executor should call only one `resolve` or one `reject`. Any state change is final.

    All further calls of `resolve` and `reject` are ignored:

    ```javascript
    let promise = new Promise(function(resolve, reject) {
      resolve("done");
    
      reject(new Error("…")); // ignored
      setTimeout(() => resolve("…")); // ignored
    });
    ```

    ```javascript
    let promise = new Promise(function(resolve, reject) {
      setTimeout(() => resolve("done!"), 1000);
    });
    
    // resolve runs the first function in .then
    promise.then(
      result => alert(result), // shows "done!" after 1 second
      error => alert(error) // doesn't run
    );
    ```

    ### [catch](https://javascript.info/promise-basics#catch)

    If we’re interested only in errors, then we can use `null` as the first argument: `.then(null, errorHandlingFunction)`. Or we can use `.catch(errorHandlingFunction)`, which is exactly the same:

    ```javascript
    let promise = new Promise((resolve, reject) => {
      setTimeout(() => reject(new Error("Whoops!")), 1000);
    });
    
    // .catch(f) is the same as promise.then(null, f)
    promise.catch(alert); // shows "Error: Whoops!" after 1 second
    ```

  - A JavaScript Promise object can be:

    - Pending
    - Fulfilled
    - Rejected

  - ```javascript
    <script>
    const myPromise = new Promise(function(myResolve, myReject) {
      setTimeout(function(){ myResolve("I love You !!"); }, 3000);
    });
    
    myPromise.then(
     function(value) {
      document.getElementById("demo").innerHTML = value;
    }
    );
    </script>
    ```

- ### JavaScript Async::

  - *"async and await make promises easier to write"*

    **async** makes a function return a Promise

    **await** makes a function wait for a Promise

  - Whenever a function awaits for any promise to be completed that function is async.

  - ```javascript
    async function rahul(){
        let wa=await promise
    }
    ```
    
    ```javascript
    async function myDisplay() {
      let myPromise = new Promise(function(resolve, reject) {
        resolve("I love You !!");
      });
      document.getElementById("demo").innerHTML = await myPromise;
    }
    
    myDisplay();
    ```
    
    ```javascript
    async function myFunction() {
      return "Hello";
    }
    myFunction().then(
      function(value) {myDisplayer(value);}
    );
    ```
    
    - **Whatever the second parameter of then or catch is rejecting is always handled by then not by catch does not matter it is error or value**
    
    ```javascript
    const myPromise = new Promise((resolve, reject) => {
      setTimeout(() => {
        reject("foo");
      }, 300);
    });
    myPromise
      .then((value) => {
        console.log(value);// this part will not run as error is getting as output.
      },
      (error) => {
        console.log("first error", error); // this part will run as error is getting.
        return error;
      }  
      )
      .catch((err) => {
        console.log("second error is ", err);// this part will not run 
        return err;
      })
      .then((val) => {
        console.log("second resolve is ", val);// this will run.
        return val;
      });
    ```
    
  - **Write a function called sleep that will return a promise, if you do not provide a number to the function, then it will return an error and goto the catch block**

    ```javascript
    function sleep(timer){
      return new Promise(function(resolve,reject){
        if(timer && typeof timer==='number'){
          setTimeout(()=>{
            resolve(`slept for ${timer} milli seconds`)
          },timer)
        }
        else{
          reject(`Timer value is missing..`)
        }
      })
    }
    ```

- **Write a program to flatten an array**

- ```javascript
  // input: [ 1, [ 2, 3 ], [ 3 ], [ [ [ 5]],  6]  ]
  // output => [ 1, 2, 3, 3, 5, 6 ]
  let input = [1, [2, 3], [3], [[[5]], 6]];
  
  const flatten = (arr) => {
    return arr.reduce((acc, curr) => {
      if (Array.isArray(curr)) {
        return acc.concat(flatten(curr));
      }
      return acc.concat(curr); // in place of concat push does not work.
    }, []);
  };
  
  let output = flatten(input);
  console.log(output);
  ```

- **Generators in JavaScript::**

- Suppose you want value from 1 to 100 but storing this much of number will use huge space. if we try use for loop in the place of generator it will give all the value at the same time. but if we want that value at any specific time we use generators.

  ```javascript
  function* Generator()
  {
    yield 1;
    yield 2;
    yield 3;  
  }
  const gen=Generator();
  console.log(gen.next().value); //1
  console.log(gen.next().value); //2
  console.log(gen.next().value); //3
  ```

  

  ```javascript
  function* Generator()
  {
      let i=0;
      while(true)
      {
        yield i;
          i++;  
      }    
  }
  const gen=Generator();
  console.log(gen.next().value); //0
  console.log(gen.next().value); //1
  console.log(gen.next().value); //2
  ```

- **Call/Apply/Bind**

  - **Call**

    - If we want to access any function of any object or any global function for any object we can use call method.

    - ```javascript
      const person = {
        fullName: function() {
          return this.firstName + " " + this.lastName;
        }
      }
      const person1 = {
        firstName:"John",
        lastName: "Doe"
      }
      const person2 = {
        firstName:"Mary",
        lastName: "Doe"
      }
      
      // This will return "John Doe":
      person.fullName.call(person1); // here person1 is calling fullName method of person object
      ```

      ```javascript
      const person = {
        fullName: function(city, country) {
          return this.firstName + " " + this.lastName + "," + city + "," + country;
        }
      }
      
      const person1 = {
        firstName:"John",
        lastName: "Doe"
      }
      
      person.fullName.call(person1, "Oslo", "Norway");//passing parameters too the functions.
      ```

  - **Apply::**

    - Same as call but difference is we can pass array of argument instead of passing individually.

    ```javascript
    const person = {
      fullName: function() {
        return this.firstName + " " + this.lastName;
      }
    }
    
    const person1 = {
      firstName: "Mary",
      lastName: "Doe"
    }
    
    // This will return "Mary Doe":
    person.fullName.apply(person1);
    ```

    ```javascript
    const person = {
      fullName: function(city, country) {
        return this.firstName + " " + this.lastName + "," + city + "," + country;
      }
    }
    
    const person1 = {
      firstName:"John",
      lastName: "Doe"
    }
    
    person.fullName.apply(person1, ["Oslo", "Norway"]);
    ```

  - **Bind()**

    - Bind basically we store function in a variable and use whenever we want it. It is exactly same as call.

    - 
    
    - ```javascript
      const person = {
        firstName:"John",
        lastName: "Doe",
        display: function () {
          let x = document.getElementById("demo");
          x.innerHTML = this.firstName + " " + this.lastName;
        }
      }
      
      let display = person.display.bind(person);// storing in display to use it later.
      setTimeout(display, 3000);
      ```

- **fetch::**

- ```javascript
  fetch('https://jsonplaceholder.typicode.com/todos/1')
    .then(response => response.json())
    .then(json => console.log(json))
  ```

  

- ```javascript
  async function fetchMoviesJSON() {
    const response = await fetch('/movies');
    const movies = await response.json();
    return movies;
  }
  ```

- **Constructor function::**

  -  the following creates a new person object with two properties `firstName` and `lastName`:

    ```javascript
    let person = {
        firstName: 'John',
        lastName: 'Doe'
    };
    ```

    you often need to create many similar objects like the `person` object.

    To do that, you can use a constructor function to define a custom type and the `new` operator to create multiple objects from this type.

    Technically speaking, a constructor function is a regular [function](https://www.javascripttutorial.net/javascript-function/) with the following convention:

    - The name of a constructor function starts with a capital letter like `Person`, `Document`, etc.
    - A constructor function should be called only with the `new` operator.

    ```javascript
    function Person(firstName, lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
    }
    ```

    ```javascript
    let person = new Person('John','Doe');
    ```

  - Basically, the `new` operator does the following:

    - Create a new empty object and assign it to the `this` variable.
    - Assign the arguments `'John'` and `'Doe'` to the `firstName` and `lastName` properties of the object.
    - Return the `this` value.

  - ```javascript
    function Person(firstName, lastName) {
        // this = {};
    
        // add properties to this
        this.firstName = firstName;
        this.lastName = lastName;
    
        // return this;
    }
    ```

  - **Calling a constructor function without the `new` keyword**

    - Technically, you can call a constructor function like a regular function without using the `new` keyword like this:

    - ```javascript
      let person = Person('John','Doe');
      ```

  - In this case, the `Person` just executes like a regular function. Therefore, the `this` inside the `Person` function doesn’t bind to the `person` variable but the [global object](https://www.javascripttutorial.net/es-next/javascript-globalthis/).

    If you attempt to access the `firstName` or `lastName` property, you’ll get an error:

    ```javascript
    console.log(person.firstName);
    TypeError: Cannot read property 'firstName' of undefined
    ```

  - **Prototype:**

    ```javascript
    const sahid = ["Kapish", "Rahul", "Sachin"];
    Array.prototype.sc = function () { // we have used prototype so will add on all the arrays.
    return this;
    };
    sahid.__proto__.newPoro = function () { // we have used proto so will add on all the arrays.
    return this.length;
    };
    const masai = [1, 2, 3, 4, 5];
    console.log(sahid.newPoro()); // 3
    console.log(masai.sc()); // [1, 2, 3, 4, 5]
    console.log(masai.newPoro()); // 5
    console.log("1234567".length);
    console.log(sahid.length);
    // which shows everything is an object in js becasuae in java string hanled in
    different way and in js it is an object
    ```

- `setTimeout(*function, milliseconds*`)

- `setInterval(*function, milliseconds*`)

- clearTimeout()

  ```javascript
  myVar = setTimeout(function, milliseconds);
  clearTimeout(myVar);
  ```

- ## What are Cookies?

  - Cookies are data, stored in small text files, on your computer.

  - When a user visits a web page, his/her name can be stored in a cookie.

  - JavaScript can create, read, and delete cookies with the `document.cookie` property.

    ```javascript
    document.cookie = "username=John Doe";
    ```

  - You can also add an expiry date (in UTC time). By default, the cookie is deleted when the browser is closed:

    ```javascript
    document.cookie = "username=John Doe; expires=Thu, 18 Dec 2013 12:00:00 UTC";
    ```

  - cookies can be read like this:

    ```javascript
    let x = document.cookie;
    ```

  - `document.cookie` will return all cookies in one string much like: cookie1=value; cookie2=value; cookie3=value;

  - Deleting a cookie is very simple.

  - Just set the expires parameter to a past date:

    ```javascript
    document.cookie = "username=; expires=Thu, 01 Jan 1970 00:00:00 UTC; path=/;";
    ```

- **The local Storage object::**

  ```javascript
  localStorage.setItem("name", "John Doe");
  localStorage.getItem("name");
  ```

- **The sessionStorage object::**

  - The sessionStorage object is identical to the localStorage object.

    The difference is that the sessionStorage object stores data for one session.

    The data is deleted when the browser is closed.

  - ```javascript
    sessionStorage.getItem("name");
    sessionStorage.setItem("name", "John Doe");
    ```

- ### JavaScript Fetch API::

  ```javascript
  async function getText(file) {
    let myObject = await fetch(file);
    let myText = await myObject.text();
    myDisplay(myText);
  }
  ```

- ***JSON format::***

  - JSON data can easily be sent between computers, and used by any programming language.

  - JavaScript has a built in function for converting JSON strings into JavaScript objects:

    ```javascript
    JSON.parse()
    ```

    JavaScript also has a built in function for converting an object into a JSON string:

    ```javascript
    JSON.stringify() 
    ```
  
- **Debouncing::**

  - Debouncing is a programming practice used to ensure that time-consuming tasks do not fire so often, that it stalls the performance of the web page. In other words, it limits the rate at which a function gets invoked.

    ```javascript
    var button = document.getElementById("debounce");
    const debounce = (func, delay) => {
        let debounceTimer
        return function() {
            const context = this
            const args = arguments
                clearTimeout(debounceTimer)
                    debounceTimer
                = setTimeout(() => func.apply(context, args), delay)
        }
    } 
    button.addEventListener('click', debounce(function() {
            alert("Hello\nNo matter how many times you" +
                "click the debounce button, I get " +
                "executed once every 3 seconds!!")
                            }, 3000));
    ```

- **Throttling::**

  - Throttling is used to call a function after every millisecond or a particular interval of time only the first click is executed immediately.

  - ```javascript
    <script>
        const btn=document.querySelector("#throttle");
         
        // Throttling Function
        const throttleFunction=(func, delay)=>{
     
          // Previously called time of the function
          let prev = 0;
          return (...args) => {
            // Current called time of the function
            let now = new Date().getTime();
     
            // Logging the difference between previously
            // called and current called timings
            console.log(now-prev, delay);
             
            // If difference is greater than delay call
            // the function again.
            if(now - prev> delay){
              prev = now;
     
              // "..." is the spread operator here
              // returning the function with the
              // array of arguments
              return func(...args); 
            }
          }
        }
        btn.addEventListener("click", throttleFunction(()=>{
          console.log("button is clicked")
        }, 1500));
      </script>
    ```

- **Bubbling**

  **When an event happens on an element, it first runs the handlers on it, then on its parent, then all the way up on other ancestors.**

  ```javascript
  <!DOCTYPE html>
  <html>
    <head>
      <title>Parcel Sandbox</title>
      <meta charset="UTF-8" />
    </head>
  
    <body>
      <div id="app"></div>
      <h2>My First JavaScript</h2>
  
      <div id="outer">
        <div id="inner">
          <div id="mostinner">
          </div>
          </div>
      </div>
  
      <script src="src/index.js"></script>
    </body>
  </html>
  ```

  ```css
  #outer 
  {
    background-color:grey;
    padding:4%;
    margin:4%;
  }
  
  #inner
  {
    background-color:yellow;
    padding:4%;
    margin:4%;
  }
  
  #mostinner 
  {
    background-color:green;
    padding:4%;
    margin:4%;
  }
  ```

  ```javascript
  const outer_id=document.getElementById("outer")
  const inner_id=document.getElementById("inner")
  const mostinner_id=document.getElementById("mostinner");
  
  outer_id.addEventListener('click',()=>{console.log('outer is clicked')})
  inner_id.addEventListener('click',()=>{console.log('inner is clicked')})
  mostinner_id.addEventListener('click',()=>{console.log('mostinner is clicked')})
  ```

- **Capturing::** It is just reverse of Bubbling. here first grandparent clicked then parent than child.

  - Just place true as the third argument of event listener.

  ```javascript
  const outer_id=document.getElementById("outer")
  const inner_id=document.getElementById("inner")
  const mostinner_id=document.getElementById("mostinner");
  
  outer_id.addEventListener('click',()=>{console.log('outer is clicked')},true)
  inner_id.addEventListener('click',()=>{console.log('inner is clicked')},true)
  mostinner_id.addEventListener('click',()=>{console.log('mostinner is clicked')},true)
  ```

- **Hoisting::**

  - **Var hoisting::**

  - JavaScript **Hoisting** refers to the process whereby the interpreter appears to move the *declaration* of functions, variables or classes to the top of their scope, prior to execution of the code.

  - ```javascript
    console.log(num); // Throws ReferenceError exception - the interpreter doesn't know about `num`.
    num = 6; // Initialization
    ```

  - Note however that initialization also causes declaration (if not already declared). The code snippet below will work, because even though it isn't hoisted, the variable is initialized and effectively declared before it is used.

    ```javascript
    a = 'Cran'; // Initialize a
    b = 'berry'; // Initialize b
    
    console.log(a + "" + b); // 'Cranberry'
    ```

  - **Let and Const::**

    - Variables declared with `let` and `const` are also hoisted but, unlike `var`, are not initialized with a default value. An exception will be thrown if a variable declared with `let` or `const` is read before it is initialized.

    - ```javascript
      console.log(num); // Throws ReferenceError exception as the variable value is uninitialized
      let num = 6; // Initialization
      ```

    - **`let`**, unlike **`var`**, does not create a property on the global object. For example:

      ```javascript
      var x = 'global';
      let y = 'global';
      console.log(this.x); // "global"
      console.log(this.y); // undefined
      ```

    - **Temporal dead zone (TDZ)::**

      - `let` variables cannot be read/written until they have been declared. If no initial value is specified on declaration, the variable is initialized with a value of `undefined`. Accessing the variable before the declaration results in a [`ReferenceError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ReferenceError).

      - The variable is said to be in a "temporal dead zone" (TDZ) from the start of the block until the declaration has completed.

      - ```javascript
        {
            // TDZ starts at beginning of scope
            const func = () => console.log(letVar); // OK
        
            // Within the TDZ letVar access throws `ReferenceError`
        
            let letVar = 3; // End of TDZ (for letVar)
            func(); // Called outside TDZ!
        }
        ```

        ```javascript
        console.log(typeof i);
        let i = 10;
        ```

        - Below will give error because foo inside if is a let and we have not initialised a value to let.

        ```javascript
        function test(){
           var foo = 33;
           if(foo) {
              let foo = (foo + 55); // ReferenceError
           }
        }
        test();
        ```

      - When used inside a block, **`let`** limits the variable's scope to that block. Note the difference between **`var`**, **whose scope is inside the function where it is declared.**

      - **The TDZ ends when `aLet` is *declared*, rather than *assigned*::**

        ```javascript
        let aLet;
        
        console.log(aLet); // undefined
        aLet = 10;
        console.log(aLet); // 10
        ```

      - Global space means window object and let and const are hoisted in the space called script so we cant access the value untill we initialise it.

    - **Const are also hoisted in temporal dead zone and gets the value undefined.**

- **What is callback hell and how to resolve it.**

  - Below is callback hell and bacause we are passing callback(a function) and that callback is also calling a callback(again a function).

  - ```javascript
    getDataFromDatabase(id, function(dataFromDatabase) {
        getDataFromWeatherAPI(dataFromDatabase.url, function(dataFromWeatherAPI) {
            saveDataToDatabase(dataFromWeatherAPI, function(result) {
                console.log("am I in hell?")
            });
        });
    });
    ```

  - We can resolve callback hell using promise. **Callback hell is the reason promises came in the picture.**

  - ```javascript
    getDataFromDatabase(id)
        .then(getDataFromWeatherAPI(dataFromDatabase.url))
        .then(saveDataToDatabase(dataFromWeatherAPI))
        .then(function(result) {
            console.log("Ah, much nicer!")
        })
        .catch(function(error) {
            console.log(error)
        });
    ```

  - **How we were doing before the promises::**

    - ```javascript
      setTimeOut(()=>{
          console.log("My first task");
          setTimeOut(
              ()=>{
                  console.log("My second task");
                  setTimeOut(()=>
                             {
                      console.log("My third task");
                  },2000)
              },2000)
      },2000)
      ```

    - So in the above example we can clearly see that inner setTimeOut is running after completion of outer setTimeOut. So basically one task is waiting for another task to complete. Promises came in the picture to resolve this issue using **.then and .catch**  and promises are more readable as compare to callback hell.

    