# Components

React applications are built from isolated pieces of UI called components. A React component is a JavaScript function that you can sprinkle with markup. Components can be as small as a button, or as large as an entire page.

* **Functional Components**: Functional components are JavaScript functions that return JSX (JavaScript XML). They are simpler and easier to write compared to class components. With the introduction of React Hooks, functional components can now manage state and side effects, making them more powerful.

```
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

Example with hooks

```
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

* **Class Components**: Class components are ES6 classes that extend React.Component. They must include a render() method that returns JSX. Class components can hold and manage state and have lifecycle methods.

```
import React, { Component } from 'react';

class Welcome extends Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

Example with State and Lifecycle Methods

```
import React, { Component } from 'react';

class Counter extends Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }

  componentDidMount() {
    document.title = `You clicked ${this.state.count} times`;
  }

  componentDidUpdate() {
    document.title = `You clicked ${this.state.count} times`;
  }

  render() {
    return (
      <div>
        <p>You clicked {this.state.count} times</p>
        <button onClick={() => this.setState({ count: this.state.count + 1 })}>
          Click me
        </button>
      </div>
    );
  }
}
```

* **Importing and exporting components**
exporting and importing components are essential for organizing your code into reusable modules. This allows you to split your application into smaller, manageable files and reuse components across different parts of your app.

    * **Exporting Components:**

    **1.Default Export:**

        1. A file can have only one default export.
        2. When importing, you can name the imported component anything you want.
        
        ```
        function Welcome(props) {
            return <h1>Hello, {props.name}</h1>;
        }

        export default Welcome;
        ```

    **2. Named Export:**

        1. A file can have multiple named exports.
        2. When importing, you must use the exact name of the exported component.

        ```
        export function Button(props) {
            return <button>{props.label}</button>;
        }

        export function Input(props) {
            return <input type="text" placeholder={props.placeholder} />;
        }
        ```

    * **Importing Components:**

    **1. Importing a Default Export:**

    ```
    import Welcome from './Welcome'; // No curly braces for default exports

    function App() {
        return (
            <div>
                <Welcome name="John" />
            </div>
        );
    }
    ```

    **2.Importing Named Exports:**

    ```
    import { Button, Input } from './Components'; // Use curly braces for named exports

    function App() {
        return (
            <div>
                <Button label="Click Me" />
                <Input placeholder="Enter your name" />
            </div>
        );
    }
    ```

    **3. Alias Imports:**
    ```
    import { Button as MyButton } from './Components';

    function App() {
        return (
            <div>
                <MyButton label="Click Me" />
            </div>
        );
    }
    ```
        


