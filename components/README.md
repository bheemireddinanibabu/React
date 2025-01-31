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