<p align="center">
  <img src = "https://media.licdn.com/dms/image/C511BAQF8F2Wry9GTXQ/company-background_10000/0/1584269093982/reactofficial_cover?e=2147483647&v=beta&t=TMIox6sTR3227DIw-2U1I_gk7cqj7xktbb2OkKNfvo4" width=900 height=300>
</p>


## 🚩 Table of Contents

- [WHY React](#why-react)
- [DOM](#dom)
- [Render](#render)
- [CLI Tools](#cli-tools) 
  1. [Vite](#vite)
- [JSX](#jsx)
- [Class Components](#class-components)
- [Life Cycle](#life-cycle)
- [Hooks](#hooks)
  - State Hooks
  - Context Hooks
  - Ref Hooks
  - Effect Hooks
  - Performance Hooks
  - Other Hooks 
  - Your own Hooks

  
--- 

## WHY React:

### Ease and Reusability of Components: 
React’s component-based structure is more than just a trendy term; it’s a revolutionary approach. Think of building your user interface like assembling lego blocks (components) that can be reused throughout your application. This not only streamlines your code and makes it more manageable, but it also significantly reduces development time. Achieving this level of modularity and reusability with vanilla JavaScript requires much more groundwork and discipline.

### Simplified State Management:
React streamlines state management in a way that vanilla JavaScript can’t compete with out of the box. The simplicity with which you can distribute data through your application using props or state management libraries (like Redux or Context API) is remarkable. This results in more predictable and easier-to-debug code, a crucial factor in the success of any project.

### A Thriving Ecosystem:
The React ecosystem is extensive and continually expanding. From routing solutions like React Router to server-side rendering with Next.js, the tools and libraries available to React developers are plentiful. This ecosystem not only speeds up development but also ensures that you’re building on top of best practices vetted by the community.

### Performance Optimization: 
React’s virtual DOM is engineered for performance. It reduces direct manipulation of the DOM, which can be a bottleneck in complex applications. This leads to faster rendering and a smoother user experience, even as your app increases in complexity.

### Robust Community Support: 
Encountering a problem? There’s a high likelihood that someone else has faced it and shared a solution. The React community is one of the most active and supportive, offering a wealth of resources, from tutorials and forums to ready-to-use components.



---



## DOM:

### What is the DOM?

The Document Object Model (DOM) is a programming interface for web documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects; that way, programming languages can interact with the page.

The DOM is not part of the JavaScript language, but is instead a Web API used to build websites. JavaScript can also be used in other contexts. For example, Node.js runs JavaScript programs on a computer, but provides a different set of APIs, and the DOM API is not a core part of the Node.js runtime.

```js
const paragraphs = document.querySelectorAll("p");
// paragraphs[0] is the first <p> element
// paragraphs[1] is the second <p> element, etc.
alert(paragraphs[0].nodeName);
```

### Disadvantages of real DOM :
Every time the DOM gets updated, the updated element and its children have to be rendered again to update the UI of our page. For this, each time there is a component update, the DOM needs to be updated and the UI components have to be re-rendered.



### What is the Virtual DOM?

The virtual DOM (VDOM) is a programming concept where an ideal, or “virtual”, representation of a UI is kept in memory and synced with the “real” DOM by a library such as ReactDOM. This process is called reconciliation.

When anything new is added to the application, a virtual DOM is created and it is represented as a tree. Each element in the application is a node in this tree. So, whenever there is a change in the state of any element, a new Virtual DOM tree is created. This new Virtual DOM tree is then compared with the previous Virtual DOM tree and make a note of the changes. After this, it finds the best possible ways to make these changes to the real DOM. Now only the updated elements will get rendered on the page again.



React uses the virtual DOM as a strategy to compute minimal DOM operations when re-rendering the UI. It is not in rivalry with or faster than the real DOM.

The virtual DOM provides a mechanism that abstracts manual DOM manipulations away from the developer, helping us to write more predictable code. It does so by comparing two render trees to determine exactly what has changed, only updating what is necessary on the actual DOM.

Like React, Vue also employs this strategy. However, Svelte proposes another approach to ensure that an application is optimized, compiling all components into independent, tiny JavaScript modules, making the script very light and fast to run.

I hope you enjoyed reading this article. Be sure to share your thoughts in the comment section if you have questions or contributions.






---



## Render:

Imagine that your components are cooks in the kitchen, assembling tasty dishes from ingredients. In this scenario, React is the waiter who puts in requests from customers and brings them their orders. This process of requesting and serving UI has three steps:

- Triggering a render (delivering the guest’s order to the kitchen)
- Rendering the component (preparing the order in the kitchen)
- Committing to the DOM (placing the order on the table)

### Step 1: Trigger a render 
There are two reasons for a component to render:

- It’s the component’s initial render.
- The component’s (or one of its ancestors’) state has been updated.

### Step 2: React renders your components 
After you trigger a render, React calls your components to figure out what to display on screen. “Rendering” is React calling your components.

- On initial render, React will call the root component.
- For subsequent renders, React will call the function component whose state update triggered the render.

### Step 3: React commits changes to the DOM 
After rendering (calling) your components, React will modify the DOM.

- For the initial render, React will use the appendChild() DOM API to put all the DOM nodes it has created on screen.
- For re-renders, React will apply the minimal necessary operations (calculated while rendering!) to make the DOM match the latest rendering output.


### Any screen update in a React app happens in three steps:
1. Trigger
2. Render
3. Commit
- You can use Strict Mode to find mistakes in your components
- React does not touch the DOM if the rendering result is the same as last time





---





## Vite:

### What's Vite:
Vite.js is a build tool that is designed to be fast and lightweight. It uses native ES modules and a native development server to provide a fast and seamless development experience. Vite. js also supports code splitting and hot reloading.

### Why Vite:
**The Problems:**

- Before native ES modules were available in browsers, developers used bundling tools (like webpack, Rollup, and Parcel) to concatenate and process source modules into browser-compatible files.
- Bundling allowed modular development but had performance limitations.
- As applications grew more complex, the amount of JavaScript increased significantly.
- Large-scale projects with thousands of modules faced performance bottlenecks.
- Dev servers took too long to start, and even with Hot Module Replacement (HMR), file edits had delays.
- In a bundler-based build setup, the dev server must eagerly crawl and build the entire application before serving it. This process can be time-consuming.

**Vite’s Approach:**

- Native ES modules support in browsers.
- JavaScript tools written in compile-to-native languages.

**Dependencies:**

- Dependencies consist mostly of plain JavaScript code that doesn’t change frequently during development.
- Some large dependencies (like component libraries with many modules) can be resource-intensive to process.
- Dependencies may be shipped in different module formats (e.g., ESM or CommonJS).
  
**Vite’s Approach:**

- Vite addresses these issues by leveraging new advancements in the ecosystem.
- It takes advantage of native ES modules (ESM) in the browser.
- Vite pre-bundles dependencies using esbuild, which is written in Go.
- This pre-bundling process is significantly faster (10-100x) than traditional JavaScript-based bundlers like webpack or Rollup.

### two major parts:

- A dev server that provides rich feature enhancements over native ES modules, for example extremely fast Hot Module Replacement (HMR).
- A build command that bundles your code with Rollup, pre-configured to output highly optimized static assets for production.



---












## JSX:

- JSX is a syntax extension for JavaScript that allows you to write HTML-like markup inside a JavaScript file.
- React developers often prefer JSX due to its conciseness, and it’s commonly used in React codebases.
- In the past, web developers kept content (HTML), design (CSS), and logic (JavaScript) separate. However, as the web became more interactive, logic started influencing content.
- In React, rendering logic and markup coexist within the same place—components.
- Components are JavaScript functions that contain markup rendered by React. JSX represents this markup, resembling HTML but with stricter rules and support for dynamic information.

### The Rules of JSX:

1. Return a single root element:

```jsx
<div>
  <h1>Hedy Lamarr's Todos</h1>
  <img 
    src="https://i.imgur.com/yXOvdOSs.jpg" 
    alt="Hedy Lamarr" 
    class="photo"
  >
  <ul>
    ...
  </ul>
</div>
```

If you don’t want to add an extra <div> to your markup, you can write <> and </> instead:

```js 
<>
  <h1>Hedy Lamarr's Todos</h1>
  <img 
    src="https://i.imgur.com/yXOvdOSs.jpg" 
    alt="Hedy Lamarr" 
    class="photo"
  >
  <ul>
    ...
  </ul>
</>
```
This empty tag is called a Fragment. Fragments let you group things without leaving any trace in the browser HTML tree.

### Close all the tags:

JSX requires tags to be explicitly closed: self-closing tags like <img> must become <img />, and wrapping tags like <li>oranges must be written as <li>oranges</li>.

```js
<>
  <img 
    src="https://i.imgur.com/yXOvdOSs.jpg" 
    alt="Hedy Lamarr" 
    class="photo"
   />
  <ul>
    <li>Invent new traffic lights</li>
    <li>Rehearse a movie scene</li>
    <li>Improve the spectrum technology</li>
  </ul>
</>
```

---














## Class Components:

### What are Class Components?
- Class components are JavaScript classes that inherit from React.Component.
- They have state, lifecycle methods, and can handle user interactions.
- Class components have been a fundamental part of React since its early days1.

### Creating a Class Component:
When creating a React class component:

- The component’s name must start with an uppercase letter.
- The component must include the extends React.Component statement, which creates an inheritance to React.Component and provides access to its functions.
- The component requires a render() method that returns HTML (JSX) representing the component’s output2.

```js
class Car extends React.Component {
  render() {
    return <h2>Hi, I am a Car!</h2>;
  }
}
```


### State and Constructor:
**State:** In React, component properties (such as data that can change) are kept in an object called state.

**Constructor:** If your component has a constructor function, it gets called when the component is initiated. You can initialize properties (like state) in the constructor.

Use the super() statement to execute the parent component’s constructor function and inherit its functions.

```js
class Car extends React.Component {
  constructor() {
    super();
    this.state = { color: "red" };
  }

  render() {
    return <h2>I am a {this.state.color} Car!</h2>;
  }
}
```

### Using State in a Class Component:
Class components can manage state using the this.state object. The state holds data that can change over time.

```js
class Counter extends React.Component {
  constructor() {
    super();
    this.state = { count: 0 };
  }

  incrementCount = () => {
    this.setState({ count: this.state.count + 1 });
  };

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={this.incrementCount}>Increment</button>
      </div>
    );
  }
}
```


### Lifecycle Methods:
- Class components have lifecycle methods that allow you to perform actions at specific points during a component’s life cycle (e.g., when it mounts, updates, or unmounts).
- Common lifecycle methods include componentDidMount, componentDidUpdate, and componentWillUnmount.

```js
class Timer extends React.Component {
  constructor() {
    super();
    this.state = { seconds: 0 };
  }

  componentDidMount() {
    this.interval = setInterval(() => {
      this.setState({ seconds: this.state.seconds + 1 });
    }, 1000);
  }

  componentWillUnmount() {
    clearInterval(this.interval);
  }

  render() {
    return <p>Seconds elapsed: {this.state.seconds}</p>;
  }
}
```

---






## Life Cycle:

### Functional Components Lifecycle Phases:
Function components have a simplified lifecycle compared to class components. They mainly focus on two phases:

- Mounting Phase: Occurs when a component is created and inserted into the DOM.
- Updating Phase: Triggers when a component’s state or props change.

### Mounting Phase:
During mounting, the following lifecycle methods are relevant for function components:

- useState: Used to manage component state within a function component.
- useEffect: Replaces lifecycle methods like componentDidMount, componentDidUpdate, and componentWillUnmount.

- useEffect runs after the initial render (similar to componentDidMount) and after every subsequent update.
- It handles side effects (e.g., data fetching, subscriptions, DOM manipulation).

```js
import React, { useState, useEffect } from 'react';

function MyComponent() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `Count: ${count}`;
  }, [count]);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

### Class Components Lifecycle Phases:

### Lifecycle Phases:
Class components go through several phases during their existence. These phases allow you to control the component’s behavior and perform specific actions at different stages.

The main lifecycle phases are:
- Mounting: Component creation and insertion into the DOM.
- Updating: Triggered when props or state change.
- Unmounting: Component removal from the DOM.

### Mounting Phase:

- During mounting, the following lifecycle methods are relevant for class components:
- constructor(): Called when the component is first created. Initialize state and bind methods here.
- render(): Generates the component’s virtual DOM representation based on current props and state.
- componentDidMount(): Invoked after the initial render. Use it for side effects (e.g., data fetching, subscriptions).

```js
import React, { Component } from 'react';

class Counter extends Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
    this.handleClick = this.handleClick.bind(this);
  }

  handleClick() {
    this.setState((prevState) => ({ count: prevState.count + 1 }));
  }

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={this.handleClick}>Increment</button>
      </div>
    );
  }
}

export default Counter;
```

### Updating Phase:
- When props or state change, the component re-renders. The following methods are relevant during updates:
- shouldComponentUpdate(nextProps, nextState): Allows you to optimize re-renders by deciding whether to proceed with the update.
- componentDidUpdate(prevProps, prevState): Executes after an update. Useful for handling side effects or additional logic.

### Unmounting Phase:
- When a component is removed from the DOM, the following method is called:
- componentWillUnmount(): Perform cleanup tasks (e.g., unsubscribing, clearing intervals) here.


---










## Hooks:

### Built-in React Hooks:

- **State Hooks **
  State lets a component “remember” information like user input. For example, a form component can use state to store the input value, while an image gallery component can use state to store the selected image index.

 **useState declares a state variable that you can update directly.**
 
 **useReducer declares a state variable with the update logic inside a reducer function.**
 
**choosing between useState and useReducer:**

We recommend using a reducer if you often encounter bugs due to incorrect state updates in some component, and want to introduce more structure to its code. You don’t have to use reducers for everything: feel free to mix and match! You can even useState and useReducer in the same component.

- https://react.dev/learn/extracting-state-logic-into-a-reducer#comparing-usestate-and-usereducer

### useState:
 - https://react.dev/reference/react/useState#updating-state-based-on-the-previous-state
 - https://www.youtube.com/watch?v=O6P86uwfdR0

### useReducer
 - https://react.dev/reference/react/useReducer
 - https://www.youtube.com/watch?v=kK_Wqx3RnHk&t=100s




- **Context Hooks**

### useContext:


  
- **Ref Hooks**

### useRef:


### useImperativeHandle:

- **Effect Hooks**

### useEffect:

### useLayoutEffect:

### useInsertionEffect:



- **Performance Hooks**


- **Other Hooks**  
   








