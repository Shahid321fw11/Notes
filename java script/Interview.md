### What are the different data types present in javascript

- **String**

  ```javascript
  var str = "Vivek Singh Bisht"; //using double quotes
   var str2 = 'John Doe'; //using single quotes
  ```

- **Number**

  ```javascript
  var x = 3; //without decimal
  var y = 3.6; //with decimal
  ```

- **Boolean**

  ```javascript
  var a = 2;
  var b =  3;
  var c =  2;
  ```

- **Undefined** - When a variable is declared but not assigned, it has the value of undefined and it’s type is also undefined.

  ```javascript
  var x; // value of x is undefined
  var y = undefined; // we can also set the value of a variable as undefined
  ```

- typeof **of primitive types**

  ```javascript
  typeof "John Doe" // Returns "string"
  typeof 3.14 // Returns "number"
  typeof true // Returns "boolean"
  typeof 234567890123456789012345678901234567890n // Returns bigint
  typeof undefined // Returns "undefined"
  typeof null // Returns "object" (kind of a bug in JavaScript)
  typeof Symbol('symbol') // Returns Symbol
  ```

- **Non-primitive types**

  Primitive data types can store only a single value. To store multiple and complex values, non-primitive data types are used.

  ```javascript
  var obj1 = {
     x:  43,
     y:  "Hello world!",
     z: function(){
        return this.x;
     }
  }
        
  // Collection of data as an ordered list
        
  var array1 = [5, "Hello", true, 4.1]; 
  ```

- **Explain Hoisting in javascript.**

- **Difference between “ == “ and “ === “ operators.**

  Both are comparison operators. The difference between both the operators is that,“==” is used to compare values whereas, “ === “ is used to compare both value and types.

  ```javascript
  var x = 2;
  var y = "2";
  (x == y)  // Returns true since the value of both x and y is the same
  
  (x === y) // Returns false since the typeof x is "number" and typeof y is "string"
  ```

- **Explain Implicit Type Coercion in javascript.**

  Implicit type coercion in javascript is automatic conversion of value from one data type to another. It takes place when the operands of an expression are of different data types.

  In the below example number is converted into string.

  ```javascript
  var x = 3;
  var y = "3";
  x + y // Returns "33" 
  ```

- **Is javascript a statically typed or a dynamically typed language?**

  JavaScript is a dynamically typed language. In a dynamically typed language, the type of a variable is checked during **run-time** in contrast to statically typed language, where the type of a variable is checked during **compile-time.**

  Here by using var we can define anything like string number boolean anything.

- **What is NaN property in JavaScript?**

  NaN property represents **“Not-a-Number”** value. It indicates a value which is not a legal number.

  ```javascript
  isNaN("Hello")  // Returns true
  isNaN(345)   // Returns false
  isNaN('1')  // Returns false, since '1' is converted to Number type which results in 0 ( a number) 
  isNaN(true) // Returns false, since true converted to Number type results in 1 ( a number)
  isNaN(false) // Returns false
  isNaN(undefined) // Returns true
  ```

- **Explain passed by value and passed by reference.**

  - In JavaScript, primitive data types are passed by value and non-primitive data types are passed by reference.

  - ```javascript
    var y = 234;
    var z = y; // good
    ```

    In the above example, assign operator knows that the value assigned to y is a primitive type (number type in this case), so when the second line code executes, where the value of y is assigned to z, the assign operator takes the value of y (234) and allocates a new space in the memory and returns the address. Therefore, variable z is not pointing to the location of variable y, instead it is pointing to a new location in the memory.

    ```javascript
    var y = #8454; // y pointing to address of the value 234
    
    var z = y; 
            
    var z = #5411; // z pointing to a completely new address of the value 234
            
    // Changing the value of y
    y = 23;
    console.log(z);  // Returns 234, since z points to a new address in the memory so changes in y will not effect z
    ```

    From the above example, we can see that primitive data types when passed to another variable, are passed by value. Instead of just assigning the same address to another variable, the value is passed and new space of memory is created.

    ```javascript
    var obj = { name: "Vivek", surname: "Bisht" };
    
    var obj2 = obj;
    ```

    In the above example, the assign operator, directly passes the location of the variable obj to the variable obj2. In other words, the reference of the variable obj is passed to the variable obj2.

- **Explain Higher Order Functions in javascript.**

  Functions that operate on other functions, either by taking them as arguments or by returning them, are called higher-order functions.

  Higher order functions are a result of functions being **first-class citizens** in javascript.

  ```javascript
  function higherOrder(fn) {
    fn();
  }
       
  higherOrder(function() { console.log("Hello world") });
  ```

- **Explain “this” keyword.**

  The “this” keyword refers to the object that the function is a property of.

  ```javascript
  function doSomething() {
    console.log(this);
  }
          
  doSomething(); // window // global object
  ```

  ```javascript
  var obj = {
      name:  "vivek",
      getName: function(){
      console.log(this.name);
    }
  }
          
  obj.getName();   // vivek
  ```

  ```javascript
  var obj = {
      name:  "vivek",
      getName: function(){
      console.log(this.name);
    }
          
  }
          
  var getName = obj.getName;
          
  var obj2 = {name:"akshay", getName };
  obj2.getName();  // akshay because now getName is part of the object obj2
  ```

- **Explain call(), apply() and, bind() methods.**

- **What is currying in JavaScript?**

- **Explain Closures in JavaScript.**

  Closures is an ability of a function to remember the variables and functions that are declared in its outer scope.

  ```javascript
  function randomFunc(){
    var obj1 = {name:"Vivian", age:45};
  
    return function(){
      console.log(obj1.name + " is "+ "awesome"); // Has access to obj1 even when the randomFunc function is executed
  
    }
  }
  
  var initialiseClosure = randomFunc(); // Returns a function
  
  initialiseClosure(); // internal function still remembers the value fo outer space
  ```

- **What are callbacks**

  Functions that are used as an argument to another function are called callback functions.

- **What is the use of a constructor function in javascript?**

  Sometimes we need a "**blueprint**" for creating many objects of the same "type".

  If we want to create multiple objects having similar properties and methods, constructor functions are used.

  The way to create an "object type", is to use an **object constructor function**.

  In the example above, `function Person()` is an object constructor function.

  Objects of the same type are created by calling the constructor function with the `new` keyword:

  ```javascript
  function Person(first, last, age, eye) {
    this.firstName = first;
    this.lastName = last;
    this.age = age;
    this.eyeColor = eye;
  }
  ```

  ```javascript
  const myFather = new Person("John", "Doe", 50, "blue");
  const myMother = new Person("Sally", "Rally", 48, "green");
  ```

  Adding a new property to an existing object is easy:

  ```javascript
  function Person(first, last, age, eye) {
    this.firstName = first;
    this.lastName = last;
    this.age = age;
    this.eyeColor = eye;
  }
  
  // Create 2 Person objects
  const myFather = new Person("John", "Doe", 50, "blue");
  const myMother = new Person("Sally", "Rally", 48, "green");
  
  // Add nationality to first object
  myFather.nationality = "English"; // allowed
  ```

  You **cannot** add a new property to an object constructor the same way you add a new property to an existing object:

  ```javascript
  function Person(first, last, age, eye) {
    this.firstName = first;
    this.lastName = last;
    this.age = age;
    this.eyeColor = eye;
  }
  
  // You can NOT add a new property to a constructor function
  Person.nationality = "English";
  ```

  

- **What are arrow functions?**

  Arrow functions are declared without the function keyword. 

  If there is only one returning expression then we don’t need to use the return keyword as well in an arrow function as shown in the example above. Also, 

  for functions having just one line of code, curly braces { } can be omitted.

  ```javascript
  var arrowMultiplyBy2 = num => num * 2;
  ```

- **Differences between declaring variables using var, let and const.**

- **What is the rest parameter and spread operator?**

  **Rest parameter ( … )**

  - Any number of arguments will be converted into an array using the rest parameter.

  - ```javascript
    function extractingArgs(...args)
    {
      return args[1];
    }
    // extractingArgs(8,9,1); // Returns 9
    extractingArgs(1,2,3,4)
    ```

  ​    **Rest parameter should always be used at the last parameter of a function:**

  ```javascript
  // Incorrect way to use rest parameter
  function randomFunc(a,...args,c){
  //Do something
  }
  
  // Correct way to use rest parameter
  function randomFunc2(a,b,...args){
  //Do something
  }
  ```

- **Spread operator (…)**

  spread operator is used to spread an array, and object literals. We also use spread operators where one or more arguments are expected in a function call.

  ```javascript
  function addFourNumbers(num1,num2,num3,num4){
    return num1 + num2 + num3 + num4;
  }
  let fourNumbers = [5, 6, 7, 8];
  addFourNumbers(...fourNumbers);
  // Spreads [5,6,7,8] as 5,6,7,8
  ```

- **What is the use of promises in javascript?**

  Promises are used to handle asynchronous operations in javascript.

  Promise object has three states -

  - Pending - Initial state of promise. This state represents that the promise has neither been fulfilled nor been rejected, it is in the pending state.

  - Fulfilled - This state represents that the promise has been fulfilled, meaning the async operation is completed.

  - Rejected - This state represents that the promise has been rejected for some reason, meaning the async operation has failed.

  - A promise is created using the **Promise** constructor which takes in a callback function with two parameters, **resolve** and **reject** respectively.

  - **resolve** is a function that will be called, when the async operation has been successfully completed.

    **reject** is a function that will be called, when the async operation fails or if some error occurs.

- **What are classes in javascript?**

  Introduced in the ES6 version, classes are nothing but syntactic sugars for constructor functions.

  They provide a new way of declaring constructor functions in javascript.

  ```javascript
  // Before ES6 version, using constructor functions
  function Student(name,rollNumber,grade,section){
    this.name = name;
    this.rollNumber = rollNumber;
    this.grade = grade;
    this.section = section;
  }
  
  // Way to add methods to a constructor function
  Student.prototype.getDetails = function(){
    return 'Name: ${this.name}, Roll no: ${this.rollNumber}, Grade: ${this.grade}, Section:${this.section}';
  }
  let student1 = new Student("Vivek", 354, "6th", "A");
  student1.getDetails();
  // Returns Name: Vivek, Roll no:354, Grade: 6th, Section:A
  
  // ES6 version classes
  class Student{
    constructor(name,rollNumber,grade,section){
      this.name = name;
      this.rollNumber = rollNumber;
      this.grade = grade;
      this.section = section;
    }
  
    // Methods can be directly added inside the class
    getDetails(){
      return 'Name: ${this.name}, Roll no: ${this.rollNumber}, Grade:${this.grade}, Section:${this.section}';
    }
  }
  
  let student2 = new Student("Garry", 673, "7th", "C");
  student2.getDetails();
  // Returns Name: Garry, Roll no:673, Grade: 7th, Section:C
  ```

- **What are generator functions?**

  Introduced in ES6 version, generator functions are a special class of functions.

  **They can be stopped midway and then continue from where it had stopped.**

  Generator functions are declared with the **function\*** keyword instead of the normal **function** keyword:

  ```javascript
  function* genFunc(){
    // Perform operation
  }
  ```

  In the case of generator functions, when called, they do not execute the code, instead they return a **generator object** . This generator object handles the execution.

  ```javascript
  function* genFunc(){
    yield 3;
    yield 4;
  }
  genFunc(); // Returns Object [Generator] {}
  ```

  The generator object consists of a method called **next()** , this method when called, executes the code until the nearest **yield** statement, and returns the yield value.

  ```javascript
  genFunc().next(); // Returns {value: 3, done:false}
  ```

  As one can see the next method returns an object consisting of **value** and **done** properties.
  Value property represents the yielded value.
  Done property tells us whether the function code is finished or not. (Returns true if finished)
  Generator functions are used to return iterators. Let’s see an example where an iterator is returned:

  ```javascript
  function* iteratorFunc() {
    let count = 0;
    for (let i = 0; i < 2; i++) {
        count++;
        yield i;
    }
    return count;
  }
  
  let iterator = iteratorFunc();
  console.log(iterator.next()); // {value:0,done:false}
  console.log(iterator.next()); // {value:1,done:false}
  console.log(iterator.next()); // {value:2,done:true}
  ```

- **Explain WeakSet in javascript.**

​    In javascript, Set is a collection of unique and ordered elements.

​    just like Set, WeakSet is also a collection of unique and ordered elements with some key differences:

​    Weakset contains only objects and no other type.

```javascript
const newSet = new Set([4, 5, 6, 7]);
console.log(newSet);// Outputs Set {4,5,6,7}

const newSet2 = new WeakSet([3, 4, 5]); //Throws an error

let obj1 = {message:"Hello world"};
const newSet3 = new WeakSet([obj1]);
```

- **What is Object Destructuring?**

  Object destructuring is a new way to extract elements from an object or an array.

  Before ES6 version

  ```javascript
  const classDetails = {
    strength: 78,
    benches: 39,
    blackBoard:1
  }
  
  const classStrength = classDetails.strength;
  const classBenches = classDetails.benches;
  const classBlackBoard = classDetails.blackBoard;
  ```

  Now

  ```javascript
  const classDetails = {
    strength: 78,
    benches: 39,
    blackBoard:1
  }
  
  const {strength:classStrength, benches:classBenches,blackBoard:classBlackBoard} = classDetails;
  
  console.log(classStrength); // Outputs 78
  console.log(classBenches); // Outputs 39
  console.log(classBlackBoard); // Outputs 1
  ```

- **What is a Temporal Dead Zone?**

  It is a behaviour where we try to access a variable before it is initialized.

- **Is JavaScript case sensitive language?**

  Yes, JavaScript is a case sensitive language. 

- **What are the variable naming conventions in JavaScript?**

  1. You should not use any of the JavaScript **reserved keyword** as variable name. For example, break or boolean variable names are not valid.
  2. JavaScript variable names should not start with a **numeral** (0-9). They must begin with a letter or the underscore character. For example, 123name is an invalid variable name but _123name or name123 is a valid one.
  3. JavaScript variable names are **case sensitive**. For example, Test and test are two different variables.

- **What is the difference between Local storage & Session storage?**

  

- **What is the difference between null & undefined?**

  Undefined means a variable has been **declared** but has not yet been **assigned** a value. On the other hand, null is an assignment value. It can be assigned to a variable as a representation of no value.

- **What is an event bubbling in JavaScript?**