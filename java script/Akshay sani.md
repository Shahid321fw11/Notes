- **Execution context::**

  - Whenever you run a java script program an execution context is created. It is just like a box which has two parts. first one is memory and second one is code part. In memory phase it allocates the memory for all the variables and functions.
  - ![image-20220102140202423](C:\Users\RAHUL AGARWAL\AppData\Roaming\Typora\typora-user-images\image-20220102140202423.png)
  - At first Global execution is created and all other execution is created inside this global execution context which is known as local execution context.

- **Call Stack:** All the execution context are put inside call stack . call stack maintains the order of execution context.

  There are other names also for call stack.

  - Execution context stack
  - Program stack
  - Runtime stack
  - Control stack
  - Machine stack

- **Java Script is loosely typed** because it can store any data type just by declaring var, const and let. Not like any other language which says string means only string.

- **Block scope and shadowing::**

  - Anything you define inside { } is block scope.

    ```javascript
    {
        var a=10;  // memory allocated in global scope.
        let b=20;   // memory allocated in block scope.
        const c=30;  // memory allocated in block scope.
    }
    console.log(a) // we can access.
    console.log(b) // we can't access.
    console.log(c) // we can't access.
    ```

  - **shadowing:**

    - value of a in block scope will override the value of var a that is known as shadowing because they both are pointing the same memory location.

    ```javascript
    var a=100;
    {
        var a=10;
        console.log(a); // output will be 10
    }
    console.log(a)// 10;
    ```

    - **Let and const** store the value in  script (memory location same like block and global memory). so variable inside block scope will override the value of a to 10(Block memory location). but outside its value will be 100 because it is pointing to the script memory location.

    ```javascript
    let a=100;
    {
        let a=10;
        console.log(a); // output will be 10
    }
    console.log(a)// 100;
    ```

  - **illegal shadowing:**

    - Whenever we try to redefine a let or const variable to var it throws an error. that is known as Illegal shadowing.

      ```javascript
      let a=10;
      {
          var a=100 // error
      }
      ```

      ```java
      var a=100;
      {
      let a=10 // allowed
      }
      ```

- **Closure:**

  - A function along with it's lexical scope is known as Closure.

  - Whenever we define a function inside another function it's always remembers the details of its lexical scope. That is known as Closure. 

  - ```javascript
    function x(){
        let a=10;
        function y()
        {
            console.log(a);
        }
        return y;
    }
    let z=x(); // now z will hold function y; after calling x execution context of x is deleted but y will still remember it.
    z() // now we are calling function z and this will print value of a even after x is not available
    ```

- **Function Statement and Function Expression.**

  **Function Statement(Function declaration)**

  ```javascript
  function a(){
      console.log("This is function Statement")
  }
  ```

  **Function expression**

  ```javascript
  var b=function (){
      console.log("This is function Expression")
  }
  ```

  **Difference between above two**

  We are calling the function before declaration so below will throw an error.

  ```javascript
  a(); // this will not throw an error.
  b(); // at the start b is undefined so calling b will throw an error.
  function a(){
      console.log("This is function Statement")
  }
  var b=function a(){
      console.log("This is function Expression")
  }
  ```

  **Named function expression**

  ```javascript
  var b=function abc(){   // here function expression has a name.
      console.log("This is function Expression")
  }
  ```

  ```javascript
  abc() // will throw an error
  ```

- **First class function:**

  - In java script function can be return from another function.
  - Function can be passed as an argument in another function.
  - This ability of the function is known as first class function. 

- **Event loop**

  ![image-20220106222318287](C:\Users\RAHUL AGARWAL\AppData\Roaming\Typora\typora-user-images\image-20220106222318287.png)

- Microsoft edge has java script engine knows as **Chakra**

- Mozilla has java script engine knows as **SpiderMonkey**

- Chrome and Node has java script engine knows as **V8** 

- Java Script is **Synchronous singly threaded.** because it has only one call stack.

- **SetTimeOut  not always right**

  - In the below example setTimeout will expire after 5 second but it will not be execute directly. First it will check whether call stack is empty or not. setTimeout will wait in callback queue for the call stack to be empty. If call stack get free after 10 second then setTimeout will be executed after 10 second.

  - ```javascript
    setTimeout(function cb(){
        console.log("Hi");
    },5000)
    ```
