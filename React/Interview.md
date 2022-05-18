**Differentiate between Real DOM and Virtual DOM. or what is Virtual DOM**

- **Document:** Any HTML file. 
- **Object:** Any tag inside HTML
- **Model:** Hierarchy of HTML file.

- **Virtual DOM** Virtual DOM is copy of the DOM which react stores in his memory. Whenever any component is changed in the DOM instead of rendering all the component of the DOM React only changes the chnaged component in the DOM.

**What is React?**

- React is a front-end JavaScript library developed by Facebook in 2011.
- It follows the component based approach which helps in building reusable UI components.

**What are the features of React?**

- It uses the **virtual DOM** instead of the real DOM.
- It uses **server-side rendering**.
- It follows **uni-directional data flow** or data binding.

 **List some of the major advantages of React.**

- Reusable Components.
- Virtual DOM concept.
- performance is good.
- SEO friendly.
- Easy to learn and  use.

### **What is JSX?**

- JSX is a shorthand for JavaScript XML.
- It allows us to write html code inside java script code.

### **Why can’t browsers read JSX?**

- Browsers can only read JavaScript objects but JSX in not a regular JavaScript object. Thus to enable a browser to read JSX, first, we need to transform JSX file into a JavaScript object using JSX transformers like Babel and then pass it to the browser.

###  **“In React, everything is a component.” Explain.**

- Components are the building blocks of a React application’s UI. 
- These components split up the entire UI into small independent and reusable pieces. 
- Then it renders each of these components independent of each other without affecting the rest of the UI.

**What is state in React::**

- *State* of a component is an object that holds some information that may change over the lifetime of the component. We should always try to make our state as simple as possible and minimise the number of stateful components.
- State is like component memoy.

**What is webpack::**

- Webpack makes a dependencies tree and bundle every component with its dependencies.

- So when we hit a url without webpack all the html css and javascript gets loaded but when we use webpack

  only related things with the component gets loaded.

- That is how webpack optimses the things.

### **What is Props?**

- Props is the shorthand for Properties in React. 
- Props is immutable.
- They are always passed down from the parent to the child components throughout the application.
-  A child component can never send a prop back to the parent component. This help in maintaining the unidirectional data flow and are generally used to render the dynamically generated data.
- Props provide a way to pass data from one component to another component. 

### **Differentiate between stateful and stateless components.**

- The component which carries state are stateful component but which does not have state or you can say which simply render UI are stateless component.
- Class or functional component both can be stateful or stateless.
- Like if a function contains useState that function is stateful component.

### **What are the different phases of React component’s lifecycle?**

- *Initial Rendering Phase:* This is the phase when the component is about to start its life journey and make its way to the DOM.
- *Updating Phase:* Once the component gets added to the DOM, it can potentially update and re-render only when a prop or state change occurs. That happens only in this phase.
- *Unmounting Phase:* This is the final phase of a component’s life cycle in which the component is destroyed and removed from the DOM.

### **What is an event in React?**

In React, events are the triggered reactions to specific actions like mouse hover, mouse click, key press, etc. Handling these events are similar to handling events in DOM elements. But there are some syntactical differences like:

1. Events are named using camel case instead of just using the lowercase.

### **What are synthetic events in React?**

imagine an event that fires when the user winks😉, this event in chrome called **A** in Safari called **B**, in such case, we will need to make different implementations for each browser😵.

What this wrapper does is registering all the different names for the same event effect, ***winking** in our case*, with only one name, so in a case when we want to listen to our winking effect instead of being listening to **A** for chrome and **B** for Safari we just use **onWink**, which is the wrapper react creates around the real event.

So whenever we are triggering an event in a React component, we are not actually dealing with the real DOM event, instead, we are dealing with React's custom event type, **a synthetic event**.

Now close your eyes😴, but not this kind of closing😅, and in your memory remember all the onClick(s), onBlur(s), onChange(s) you have ever used in your react components, these are not the real ones, these are react's synthetic events😇.

### **What do you know about controlled and uncontrolled components?**

- In a controlled component, **form data is handled by** a React component. Like using onChange event and passing event to it and getting data using **event.target.value.**

  - In controlled component when we change anything in input field state value is changed like using setState we set the value of input filed in the state but if we change the value of setState value somehow value of input field is also changed.

  - In the below example whatever the value in input box; it is coming in value using handlechange function.

  - Same when we are changing the value of setState using button the same value will also be apply in input field.

  - So basically component is controlling the value of input field.

    ```jsx
    const [value,setValue]=useState("");
    <input type="text" value={value} onChange={handleChnage}>
    function handlechange()
    {
        setValue(e.target.value);
    }    
    <button onClick{handleButton}> Click me </button>
    function handleButton()
        {
            setValue("My name is Rahul")
        }    
    ```

    

- The alternative is uncontrolled components, where form data is handled by the DOM itself. To write an uncontrolled component, instead of writing an event handler for every state update, **you can use a ref to get form values from the DOM.**


###  **What is the significance of keys in React?**

### **How is React Router different from conventional routing?**

- In conventional routing we move from one file to another file but in React Router we show the component in the same file or same HTML page.

### What are fragments?

-  In React, Fragments are used for components to return multiple elements. It allows you to group a list of multiple children without adding an extra node to the DOM.

- ```jsx
  render() {  
    return (  
      <React.Fragment>  
        <ChildA />  
        <ChildB />  
        <ChildC />  
      </React.Fragment>  
    )  
  }  
  ```

  









