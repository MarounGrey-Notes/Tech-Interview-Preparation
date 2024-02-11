# React Interview Questions
React has become one of the most widely used frontend frameworks. Having a strong grasp of React’s core principles is key for success in React interviews. This section covers common React interview questions.

![React Logo](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fcdn.freebiesupply.com%2Flogos%2Flarge%2F2x%2Freact-1-logo-png-transparent.png&f=1&nofb=1&ipt=5fd91e3622bbb8346995c339b676eb5485e0e167711ab651a1e90d602540ce1a&ipo=images)


## Glossary
**Components** - Reusable, independent pieces of UI logic and rendering. Building blocks of React UIs.

**Props** - Read-only data passed from parent to child components. Customize components and enable reuse.

**State** - Mutable data managed inside component. Triggers re-renders when updated.

**Hooks** - Functions like useState() to use React features in function components.

**JSX** - HTML-like syntax for rendering UI by mixing HTML and JavaScript.

**Virtual DOM** - In-memory representation of Real DOM. Enables fast comparison and selective UI updates.

**Reconciliation** - Algorithm to diff Virtual DOM versions to selectively update real DOM elements.

**HOC** - Higher Order Component. Advanced component taking another component to enhance it. 

**Babel** - Transpiles modern JavaScript to be compatible with older browsers. 

**Webpack** - Bundles all project assets. Allows importing CSS, images etc in JS.

**React Router** - A declarative routing library for React that helps map URLs to UI components to enable multiple "pages" without full page reloads.

---------

## Interview Questions
### What are major React components?
Elements - The smallest building blocks of React apps. Can describe HTML dom elements or user-defined React components. Often created via JSX. Renders to DOM.

Components - Independent, reusable pieces of UI logic. Define their own rendering logic and structure. Receives data via props, maintain state and lifecycles. Building blocks of UIs.

Props - Read-only data passed from parent component to child component(s). Allows customizing components and reuse. Child cannot modify props.

State - Mutable data within component. Defined and updated directly in component via state hook or this.setState. Triggers re-renders when modified. Local to the component.

JSX - HTML-like syntax that gets transpiled to React.createElement() calls. Makes visual component rendering easy by mixing UI markup with logic.

### Difference between props and state. When to use what.
**Props:**

- Passed from parent component to child components
- Function parameters
- Cannot be changed by child components
- Changes happen outside component

*Use props for:*

- *Passing data to customize components*
- *Making components reusable*

**State:**

- Managed inside the component
- Can be changed inside component
- Triggers re-render when updated
- Makes component dynamic

*Use state for:*

- *Managing data that changes in component*
- *Rerendering component when internal data changes*
- *Keeping track of input forms, toggles etc*

**In summary:**

- Props make components reusable from outside
- State makes components reusable from inside

```jsx
// Parent Component
function Parent(props) {
  return <Child name="John" age={12} /> 
}

// Child Component
function Child(props) {
  
  // props are passed from parent 
  const [stage, setStage] = useState("infant");  

  return (
    <div>
      {/* Rendering props */}
      <h1>Name: {props.name}</h1>  
      <h2>Age: {props.age}</h2>

      {/* Using state */}
      <h3>Stage: {stage}</h3>
      
      {/* Updating state */}
      <button onClick={() => setStage("teen")}>
        Grow Up  
      </button>
    </div>
  );
}
```
**In this example:**

- name and age values are passed as props from parent. They render in child but can't be changed by child.
- stage value is local state inside child. It initializes to "infant" but can be updated via setStage inside child.

So child depends on props for external, customizable data from parent. And also manages its own state that parent can't modify.


### What are lifecycle methods in React? Explain some common methods like componentDidMount, shouldComponentUpdate etc.

**componentDidMount** - Called after the component is rendered for the first time. This is where you can put API calls, set up subscriptions, or update DOM elements like measurements etc since now the component is mounted to the real DOM.

**shouldComponentUpdate** - Called before re-rendering component when there is a change in state or props. Returns boolean to determine if re-rendering should occur. Skips unnecessary updates for better performance.

**componentDidUpdate** - Called immediately after a component re-renders after an update. Can compare previous and current props/state here. Place to operate on the DOM when the component has been updated.

**componentWillUnmount** lifecycle - Just before unmounting component from DOM. Perfect place for cleanup like invalidating timers, canceling network requests, removing event handlers etc related to that component.

**getDerivedStateFromProps** - Invoked right before calling render method including after new props or state is received. Returns object to update state.

So in summary, lifecycle methods provide hooks to perform actions during key phases of a component's existence and update cycle. We can optimize performance and manage side effects well using them.


Here is an example component demonstrating some common React lifecycle methods with sample usage:

```jsx
class Profile extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      userData: null
    };
  }

  componentDidMount() {
    // Fetch user data from API
    fetchUserData().then(data => {
      this.setState({userData: data});  
    });
  }

  shouldComponentUpdate(nextProps, nextState) {
     // Only re-render if user data changes
     if (this.state.userData !== nextState.userData) {
        return true;
     }
     return false; 
  }

  componentDidUpdate(prevProps, prevState) {
    // Use effect after state update 
    document.title = this.state.userData.name;
  }

  componentWillUnmount() {
    // Clean up
    clearUserDataCache(this.state.userData.id) 
  }

  render() {
    return <div>{this.state.userData.name}</div> 
  }
}
```

So we:
- Fetch initial data in `componentDidMount`
- Conditionally render in `shouldComponentUpdate` 
- Post-render update DOM/state in `componentDidUpdate`  
- Clear caches before unmount in `componentWillUnmount`


### How does React implement one way data binding under the hood? Explain why immutability is important in React.
React uses a technique called Virtual DOM Diffing. It maintains a lightweight virtual representation of the actual DOM in memory. When state changes, it creates a new virtual DOM tree and diffs against the previous virtual DOM snapshot to find what actually changed.

It then selectively updates only those changed DOM elements in the real DOM, rather than re-rendering everything.

This means that when props or state changes, React will trigger a re-render by default as it has no way of knowing what caused the the change or what impact it has on other data.

This is why immutability matters in React. If we directly mutate state, React's shallow checking mechanism can't detect the change. By treating state and props as immutable and always generating new copies with changes, we ensure change detection works properly.

For example:

```
// Anti-pattern
this.state.users.push(newUser); 

// Better approach 
this.setState({ 
    users: [...this.state.users, newUser] 
})
```

We return a new copy of state rather than mutate existing one. This lets React know data changed internally so it can update DOM accordingly.

So in summary, React builds optimization capabilities assuming immutability. By avoiding mutation, virtual DOM reconciliation works properly.

### Explain concepts like Virtual DOM, Reconciliation, React Fiber etc.

**Virtual DOM** - In-memory representation of the actual DOM structure. Lets React avoid manipulating real DOM which is slower. Compares current and previous virtual DOM state to selectively figure out minimal component updates.

**Reconciliation** - The algorithm React uses to diff one virtual DOM tree with another to figure out what elements need to be changed. Does efficient subtree traversal to reduce comparisons. Leverages keys to match children.

**Fiber** - The new reconciliation engine in React 16 that has improved incremental rendering by splitting work into chunks and being able to pause/resume work to prevent blocking browser paints/updates. Enables new concurrency capabilities.

**Fiber Root** - A node that forms the parent/container of a React subtree within which all work is done. An app may have multiple of these. Updates inside don't affect outside or vice-versa.

In summary - React maintains a virtual representation of UI, compares differences each time state changes, and selectively updates the real UI accordingly for performance. Concepts like reconciliation, fiber make this possible.


### When would you use a Class vs Function component?
Here is a quick summary of when to use a Class vs Function component in React:

**Function Components**
- Simple components without state or lifecycle methods
- Mainly responsible for accepting props and rendering UI
- Easy to read and test
- Often refactored to reuse logic (custom hooks, HOCs)

**Class Components** 
- Need to manage private internal state
- Complex UI logic and lifecycle hooks 
- Integrate with state management like Redux
- Legacy codebases with class components

Since the introduction of React Hooks, Function components can also use state and other features.

So in most cases, Function components should be preferred due to their simplicity. Use Class components when you specifically need internal stateful behavior and lifecycle capabilities.

The general rule of thumb is start with function components. Refactor to classes only if truly needed for lifecycles, state or performance optimizations.

### What are React Hooks? When were they introduced and why? Explain useState, useEffect hooks etc.
**What** - Functions allowing function components to use state and other React features previously only available in classes like lifecycle methods. 

**When** - React 16.8 in early 2019. Allowed writing entire components with functions. Avoid class confusion and reuse common logic.

**useState** - Returns stateful value and setter for managing state in function components. Creates encapsulated state.

```jsx
const [count, setCount] = useState(0); 
```

**useEffect** - Runs after render lifecycle. Useful for side effects like API calls, subscriptions:  

```jsx  
useEffect(() => {
  document.title = `Messages (${count})`;
}, [count]);
```

**useContext** - Accepts a context object and returns current context value to allow sharing data without prop drilling.

**useCallback** - Returns memoized callback preventing unnecessary re-renders when passed as props.

So in summary hooks unlocked stateful behavior in function components. No need for classes in most cases anymore!


### How to conditionally render components in React?
**1. If/Else**

You can use simple JavaScript conditional logic inside render:

```jsx
function App() {
  const isLoggedIn = true;
  
  if (isLoggedIn) {
    return <WelcomeMessage />
  } else {
    return <LoginForm />
  }
}
```

**2. Ternary operator**

Shorter syntax with the ternary operator:


```jsx
function App() {

  return loggedIn ? <Welcome /> : <Signup />;
  
}
```

**3. && operator**

Including components conditionally with logical && operator:

```jsx 
function App(){

  return (
    loggedIn && <UserDetails />        
  )
}
```

If condition on left is true, component on right is rendered.

**4. IIFEs**

Immediately Invoked Function Expressions:

```jsx
function App() {
  
  return (
    loggedIn && (
      () => {
        return <UserDetails />
      })()  
  ) 
}
```

Helpful to group JSX without adding extra nested elements.

So in summary, leveraging JavaScript operators, functions and standard conditional logic facilitates dynamic rendering.

### What are Higher Order Components? Give an example.
Higher Order Components (HOCs) are advanced React components that take a component as an argument and return an enhanced/modified version of that component.

For example, here is HOC that logs component props to console:

```jsx
// HOC 
function logProps(WrappedComponent) {
  return class extends React.Component {
    componentDidUpdate(prevProps) {
      console.log('Current props: ', this.props);
      console.log('Previous props: ', prevProps);
    }
    render() {
      return <WrappedComponent {...this.props}/>
    }
  }
}

// Enhanced component
const EnhancedComponent = logProps(OriginalComponent); 
```

Some ways HOCs are useful:

- Code reuse and abstraction 
- Render hijacking
- State abstraction and manipulation
- Props manipulation

HOCs allow you to reuse common non-visual behavior easily across components.


### How to communicate between sibling or parent/child components in React?
✅ **1. Lifting the State Up**: Share common state between components by lifting the state to the common parent component, and pass down state values and actions through props. Parent acts as single source of truth:

```jsx
// Parent
function Parent() {
   const [selected, setSelected] = useState(2);
  
   return (
       <Child1 selected={selected}>
       <Child2 onSelect = {setSelected} />
   )
} 
```

✅ **2. With React Context:** Allows creating global state to easily retrieve state anywhere in the component tree. Avoid prop drilling. Lets you subscribe directly to context changes:

```jsx
const UserContext = createContext(); 

// Parent
<UserContext.Provider value={user}>
  <Child1 />
  <Child2 />  
</UserContext.Provider>

// Inside Child2
const user = useContext(UserContext);
```

✅ **3. Using Redux:** With global app store and actions for highly scalable apps with complex state. Integrates React and Redux.

So in summary, lifting state, React context, and Redux help components communicate state changes in a decoupled manner.

### What are some ways to optimize React app performance?

⚛️ **Use Production Build:** The development build contains warnings and helpful console messages. But it is slower due to extra code needed for tooling. The production build optimizes performance with faster code execution and smaller bundle sizes.

⚛️ **Virtualize Long Lists:** Use windowing libraries like react-window or react-virtualized to render only visible portion of long lists. Avoid over-rendering. 

⚛️ **Memoization:** Wrap function components in `React.memo` to skip re-rendering if props did not change. Also helps avoid unnecessary recalculations.

⚛️ **Lazy load components:** Use dynamic `React.lazy` and `Suspense` to lazy load non-critical components to reduce initial bundle size.

⚛️ **Pagination:** Use pagination, infinite scroll, or load next page on request rather than showing all records on single page to optimize loading time.

⚛️ **Optimize images:** Use smaller optimized images, lazy load offscreen images, use SVG where possible. 

⚛️ **Code splitting:** Break code into smaller chunks loaded on demand to avoid users downloading unused code for first render.


### Discuss React build setup using Babel and Webpack from scratch.
Here is a quick overview of setting up a React build process from scratch using Babel and Webpack:

**Initialize Project**

Start by creating a new project folder, initializing NPM for managing dependencies, and installing React:

```
mkdir my-react-app
cd my-react-app
npm init -y
npm install react react-dom
```

**Install Babel**

Babel transpiles your ES6 JavaScript code to ES5 for broader browser compatibility.

```
npm install @babel/core @babel/cli @babel/preset-env @babel/preset-react --save-dev
```

Create `.babelrc` config file to specify presets:

```json
{
  "presets": ["@babel/env","@babel/react"]  
}
```

**Configure Webpack** 

Webpack will bundle all assets. Install webpack and webpack-cli packages:

```
npm install webpack webpack-cli --save-dev
```

Add `build` and `dev` scripts to `package.json` to run webpack:

```json
"scripts": {
  "build": "webpack", 
  "dev": "webpack serve"
}
```

Create `webpack.config.js` file to process js through babel-loader: 

```js
module.exports = {
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /node_modules/,  
        use: {
          loader: 'babel-loader'
        }
      }
    ]
  }
}
```

And that's it! Run `npm run dev` and start coding in `src` folder.

