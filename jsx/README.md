# JSX

JSX (JavaScript XML) is a syntax extension for JavaScript that allows you to write HTML-like code in your JavaScript files. It is commonly used in React to define the structure and appearance of components. JSX makes it easier to visualize and work with the UI components in your React application.

* JSX is not HTML, but it looks similar.
* It is a syntax sugar for calling React.createElement().
* JSX is transpiled into regular JavaScript by tools like Babel before being executed in the browser.

```
function Greeting() {
  return <h1>Hello, World!</h1>;
}
```

* This JSX code is transpiled into:
```
function Greeting() {
  return React.createElement("h1", null, "Hello, World!");
}
```
## Key Features of JSX:

  **1. Embedding Expressions:**
  You can embed JavaScript expressions inside JSX using curly braces {}.
    
  ```
  function Greeting(props) {
      return <h1>Hello, {props.name}!</h1>;
  }
  ```

  **2. Self-Closing Tags:**
  In JSX, tags without children must be self-closed, similar to XML.
  
  ```
  <img src="image.jpg" alt="Description" />
  ```
    
  **3. Class vs. ClassName:**
  Since class is a reserved keyword in JavaScript, JSX uses className instead.
  
  ```
  <div className="container">Content</div>
  ```

  **4. Inline styles:**
  Inline styles are written as an object, with camelCased property names.
  
  ```
  <div style={{ color: 'red', fontSize: '20px' }}>Styled Text</div>
  ```

  **5. Fragments:**
  JSX requires a single root element. If you don’t want to add an extra DOM element, you can use a React Fragment.
  
  ```
  function App() {
      return (
          <>
              <h1>Title</h1>
              <p>Description</p>
          </>
      );
  }
  ```

## JSX Rules:
    
  * One Root Element: JSX must have a single root element. Use a <div> or a fragment (<>...</>) to wrap multiple elements.
  * Close All Tags: All tags must be closed, either with a closing tag (</div>) or as a self-closing tag (<img />).
  * Use camelCase for Attributes: HTML attributes like class and for become className and htmlFor in JSX.
  * JavaScript Expressions in Curly Braces: Use {} to embed JavaScript expressions.

## Why Use JSX?

  * Readability: JSX is easier to read and write compared to React.createElement().
  * Familiarity: It looks like HTML, making it intuitive for developers.
  * Powerful: You can embed JavaScript expressions and logic directly in the markup.
      
