**Hooks always should be inside of a function**

**useState( )**

- Whenever we update the value of setCount value of count is updated.

```javascript
import { useState } from "react"
const App=()=>
{
    const [count,setCount]=useState(0) // here 0 is initial value
    <button onClick={setCount(count+1)}> click me</button>
    <button onClick={my_funct}> click me</button>
}
export default App;
```

- **Watch video 39(#36) again **

- We can also pass object in useState()

- ```javascript
  import { useState } from "react"
  const App=()=>
  {
      const [count,setCount]=useState({
          name="",
          email="",
      }) // here 0 is initial value
      //<button onClick={setCount(count+1)}> click me</button>
      <input type="text" name="abc" onChange={my_funct}>
      <button onClick={my_funct}> click me</button>
  }
  my_funct(){
      const {name,value}=event.target; //we are getting name and value from input field.
      setCount((count)=>{
          return{
              ...count,
              [name]=value,
          }
      })
  }
  export default App;
  ```

- **Context API**

  - There are three parts  

    - CreateContext

    - Provider

    - Consumer

    - ```javascript
      # App.jsx
      import React,{ createContext } from "react"
      import ComA from "./ComA"
      
      const FirstName =createContext();
      const LastName =createContext();
      
      const App = () =>
      {
          return
      (   <>
          <FirstName.Provider value={"Vinod"}>
          <LastName.Provider value={"Thapa"}>
          </ComA>
          </LastName.Provider>  
          </FirstName.Provider>  
          </>
      )        
      }
      
      export default App;
      export {FirstName,LastName};
      ```

      ```javascript
      # ComA
      import React from "react"
      import { FirstName, LastName } from "./App"
      
      const ComA=()=>{
          const fname=useContext(FirstName);
          const lname=useContext(LastName);
          return (
          <h1>
              My name is {fname}{lname}
          </h1>    
          );
      }
      ```

- **useEffect:**

  - If you want to perform any activity after rendering you can use useEffect.

  - `useEffect` accepts two arguments. The second argument is optional.

    ```javascript
    useEffect(<function>, <dependency>)
    ```

    ```jsx
    // here is no dependecies on useEffect so useEffect will run at every render.
    // in below example useEffect value of count is changing after each rendering.
    import { useState, useEffect } from "react";
    import ReactDOM from "react-dom";
    
    function Timer() {
      const [count, setCount] = useState(0);
    
      useEffect(() => {
        setTimeout(() => {
          setCount((count) => count + 1);
        }, 1000);
      });
    
      return <h1>I have rendered {count} times!</h1>;
    }
    
    ReactDOM.render(<Timer />, document.getElementById('root'));
    ```

    ```jsx
    useEffect(() => {
      //Runs only on the first render
    }, []);
    ```

    ```jsx
    useEffect(() => {
      //Runs on the first render
      //And any time any dependency value changes
    }, [prop, state]);
    ```

- **LifeCycle of react component::**

  - Mounting

  - Unmounting

  - Updation // for updating don't use dependencies. 

  - ```jsx
    useEffect(
    {
    ()=>console.log("Hi I am mounted"); // when component is mounted.
    return ()=>console.log("Hi I am unmounted") // when component is unmounted.
    },[])
    ```

- **React Router**

  ```jsx
  npm i react-router-dom
  ```

  ```jsx
  import ReactDOM from "react-dom";
  import { BrowserRouter, Routes, Route } from "react-router-dom";
  import Layout from "./pages/Layout";
  import Home from "./pages/Home";
  import Blogs from "./pages/Blogs";
  import Contact from "./pages/Contact";
  import NoPage from "./pages/NoPage";
  
  export default function App() {
    return (
      <BrowserRouter>
        <Routes>
          <Route path="/" element={<Layout />}>
            <Route index element={<Home />} /> // understand this line
            <Route path="blogs" element={<Blogs />} />
            <Route path="contact" element={<Contact />} />
            <Route path="*" element={<NoPage />} />
          </Route>
        </Routes>
      </BrowserRouter>
    );
  }
  
  ReactDOM.render(<App />, document.getElementById("root"));
  ```

- `<Link>` is used to set the URL and keep track of browsing history.

  Anytime we link to an internal path, we will use `<Link>` instead of `<a href="">`.

  ```jsx
  import { Outlet, Link } from "react-router-dom";
  
  const Layout = () => {
    return (
      <>
        <nav>
          <ul>
            <li>
              <Link to="/">Home</Link>
            </li>
            <li>
              <Link to="/blogs">Blogs</Link>
            </li>
            <li>
              <Link to="/contact">Contact</Link>
            </li>
          </ul>
        </nav>
  
        <Outlet />
      </>
    )
  };
  
  export default Layout;
  ```

  **How to pass any value from Router:**

  ```jsx
  <BrowserRouter>
        <Routes>
          <Route path="/" element={<Layout />}>
              
            // Here we are passing name as Rahul from Route 
            <Route path="blogs" element={()=><Blogs name="Rahul"/>} />
            
            <Route path="contact" element={<Contact />} />
            <Route path="*" element={<NoPage />} />
          </Route>
        </Routes>
      </BrowserRouter>
  ```

- **useParams:**

  - Suppose we pass some other details along with path then we use useParams.

  - ```jsx
    <BrowserRouter>
          <Routes>
            <Route path="/" element={<Layout />}>
                
              <Route path="contact/:fname/:lname" element={<Contact />} />
              <Route path="*" element={<NoPage />} />
            </Route>
          </Routes>
        </BrowserRouter>
    ```

    ```jsx
    import { useParams } from "react-router-dom";
    
    const User=()=>{
        const {fname,lname}=useParams();
        return(
        <h1>My name is {fname} {lname}</h1>
        );
    };
    
    ```

- **useLocation:**

  ```jsx
  import { useLocation } from "react-router-dom";
  const location=useLocation();
  console.log(location.pathname); // 'user/vinod/thapa'
  ```

- **useHistory**

  - We can move forward and backward direction in url using this hook.

- **useRef**

  - Suppose we want to access value of an input field so we can use useRef hook.

  - ```jsx
    const luckyName=useRef(null);
    // here luckyName will give the all the fields of input box and you can access that using luckyName.current.fieldName. 
    <input type="text" id="luckyName" ref={ luckyName }>
    const Name=luckyName.current.value; 
    ```

- **Redirect:**

  ```jsx
  import "./App.css";
  import {
    BrowserRouter as Router,Switch,Route,Redirect,} from "react-router-dom";
    
  
  import Home from "./components/Home";
  import About from "./components/About";
  import ContactUs from "./components/ContactUs";
    
  function App() {
    return (
      <>
        {/* This is the alias of BrowserRouter i.e. Router */}
        <Router>
          <Switch>
            
            <Route exact path="/" component={Home} />
            <Route path="/about" component={About} />
            <Route path="/contactus" component={ContactUs} />
            // If any unmatched url is passed then Redirect to home page.
            <Redirect to="/" /> 
          </Switch>
        </Router>
      </>
    );
  }
    
  export default App;
  ```

  ```jsx
  <Route exact path="/">
    {loggedIn ? <Redirect to="/dashboard" /> : <PublicHomePage />}
  </Route>
  ```

- **How to perform action on resize of the windows**

  ```javascript
  <!DOCTYPE html>
  <html>
  <body onresize="myFunction()">
  
  <p>Try to resize the browser window to display the windows height and width.</p>
  
  <p id="demo"></p>
  <script>
  function myFunction() {
    var w = window.outerWidth;
    var h = window.outerHeight;
    var txt = "Window size: width=" + w + ", height=" + h;
    document.getElementById("demo").innerHTML = txt;
  }
  </script>
  
  </body>
  </html>
  ```

- **Conditional rendering::**

  - ```jsx
    export default function App() {
      const [count, setCount] = useState(0);
      const check=()=>{
        if(count===5)return <h1>I am in</h1>
        else return <h1>I am out</h1>
      }
    
      return (
        <div className="App">
          <h1>Hello CodeSandbox</h1>
          <h2>Start editing to see some magic happen!</h2>
          <button onClick={() => setCount(count===5?4:5)}>Click me2</button>
          {count===5 && <CompA/>} // conditional rendering.
          {check()} // conditional rendering using function.
        </div>
      );
    }
    ```

- **useMemo::**

  - Suppose in a component there are some functions and we want to call that functions only at some specific condsitions than we can use useMemo.
  - In the below function calculate function will be called everytime component is render.

  ```jsx
  import { useState } from "react";
  import ReactDOM from "react-dom/client";
  
  const App = () => {
    const [count, setCount] = useState(0);
    const [todos, setTodos] = useState([]);
    const calculation = expensiveCalculation(count);
  
    const increment = () => {
      setCount((c) => c + 1);
    };
    const addTodo = () => {
      setTodos((t) => [...t, "New Todo"]);
    };
  
    return (
      <div>
        <div>
          <h2>My Todos</h2>
          {todos.map((todo, index) => {
            return <p key={index}>{todo}</p>;
          })}
          <button onClick={addTodo}>Add Todo</button>
        </div>
        <hr />
        <div>
          Count: {count}
          <button onClick={increment}>+</button>
          <h2>Expensive Calculation</h2>
          {calculation}
        </div>
      </div>
    );
  };
  
  const expensiveCalculation = (num) => {
    console.log("Calculating...");
    for (let i = 0; i < 1000000000; i++) {
      num += 1;
    }
    return num;
  };
  
  const root = ReactDOM.createRoot(document.getElementById('root'));
  root.render(<App />);
  ```

  - We can use useMemo to optimse it.

  ```jsx
  import { useState, useMemo } from "react";
  const calculation = useMemo(() => expensiveCalculation(count), [count]); # now this will be called only after any chnage in count variable.
  ```
  
- **memo--> not useMemo::**

  - If we want to render any component only when there is a change in the props of that component than we can use React.memo.

  - ```jsx
    const App = () => {
      const [count, setCount] = useState(0);
      const [todos, setTodos] = useState(["todo 1", "todo 2"]);
    
      const increment = () => {
        setCount((c) => c + 1);
      };
    
      return (
        <>
          <Todos todos={todos} /> // this child component will be render everytime App renders. 
          <hr />
          <div>
            Count: {count}
            <button onClick={increment}>+</button>
          </div>
        </>
      );
    };
    ```

    ```jsx
    # Todo.jsx
    import { memo } from "react";
    
    const Todos = ({ todos }) => {
      console.log("child render");
      return (
        <>
          <h2>My Todos</h2>
          {todos.map((todo, index) => {
            return <p key={index}>{todo}</p>;
          })}
        </>
      );
    };
    
    export default memo(Todos); // now this will be render only when there is any change in the props.
    ```

- **useCallback::**

  - If we are using memo than component will ony be render if there is any change in the prop.

  - When we are passing any function from parent component to child component so evry time parent component re-render every function of the parent component will be considered as new or we can say will be newlycreated so if weare passing function as prop child component will think it is updated function and will be re-render. 

  - So to avoid this we use **useCallback**..

  - **useCallback** take some dependencies and allows to recreate that function only that dependency is changed.

  - ```jsx
    const App = () => {
      const [count, setCount] = useState(0);
      const [todos, setTodos] = useState([]);
    
      const increment = () => {
        setCount((c) => c + 1);
      };
      const addTodo = useCallback(() => {
        setTodos((t) => [...t, "New Todo"]);
      }, [todos]); // now whenever App re-render and there is any change in the todos this function will be re-render and child component will be called.
    
      return (
        <>
          <Todos todos={todos} addTodo={addTodo} />
          <hr />
          <div>
            Count: {count}
            <button onClick={increment}>+</button>
          </div>
        </>
      );
    };
    ```

    ```jsx
    import { memo } from "react";
    
    const Todos = ({ todos, addTodo }) => {
      console.log("child render");
      return (
        <>
          <h2>My Todos</h2>
          {todos.map((todo, index) => {
            return <p key={index}>{todo}</p>;
          })}
          <button onClick={addTodo}>Add Todo</button>
        </>
      );
    };
    
    export default memo(Todos);
    ```
