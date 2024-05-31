<p align="center">
  <img src = "https://media.licdn.com/dms/image/C511BAQF8F2Wry9GTXQ/company-background_10000/0/1584269093982/reactofficial_cover?e=2147483647&v=beta&t=TMIox6sTR3227DIw-2U1I_gk7cqj7xktbb2OkKNfvo4" width=900 height=300>
</p>


## 🚩 Table of Contents

- [Vite](#vite)
- [JSX](#jsx)
- [Class Components](#class-components)
- [Life Cycle](#life-cycle)
- [Hooks](#hooks)

  
--- 

run _npx create-react-app my-app_ it automatically installs the latest version of Create React App.

If you've previously installed create-react-app globally via _npm install -g create-react-app_


## Vite

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



