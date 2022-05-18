- **What is Babel**

  - Babel is a kind of complier which converts the java script code to the code that is understandable by the browser.
  - Babel comes by default with react.
  - ![image-20220109150044082](C:\Users\RAHUL AGARWAL\AppData\Roaming\Typora\typora-user-images\image-20220109150044082.png)

- **Hello world in react**

  ![image-20220109150450531](C:\Users\RAHUL AGARWAL\AppData\Roaming\Typora\typora-user-images\image-20220109150450531.png)

- **JSX--> Java Script XML**

- 

- ```jsx
  npx create-react-app my-app
  cd my-app
  npm start
  ```

- **React Fragment::** To make all the component a single component we use React Fragment

  ![image-20220109155939572](C:\Users\RAHUL AGARWAL\AppData\Roaming\Typora\typora-user-images\image-20220109155939572.png)

- **How to pass a value from a variable to JSX:**

  ![image-20220109173937232](C:\Users\RAHUL AGARWAL\AppData\Roaming\Typora\typora-user-images\image-20220109173937232.png)

- In react in place of class use className

- ```javascript
  export default one; // at the time of import we can use any value in place of one
  export {two,three}
  ```

  ```javascript
  import {two,three} from  "./filename"
  import one from "./filename" // no need to add {} in default values
  ```

- **How to pass custom element in the component**

  ```javascript
  import React from 'react';
  import ReactDom from 'react-dom';
  
  function Card(props){
      return(
      <>
      console.log({props.image});    
      </>    
  )       
  }
  -------------------
  ReactDom.render(
  <>
     <Card 
    image="abc"
    title="xnt"
    sname="ass"
    link="hgh"  
      />
  </>,
  document.getElementById("root")   
  );
  ```
  
  - We can also use component like below . The statement inside the Component is called children.
  
  ```jsx
  <CompA>Hello Rahul</CompA>
  
  # CompA
  const CompA=(props)=>
  {
      <p>{props.children}</p>   
  }
  ```
  
  
