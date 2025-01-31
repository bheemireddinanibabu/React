# Props

Props (short for "properties") are a fundamental concept in React that allow you to pass data from a parent component to a child component. Props are read-only, meaning that a child component cannot modify the props it receives. They are used to make components dynamic and reusable.

## What Are Props?

* Props are immutable (cannot be changed by the child component).
* They are passed from a parent component to a child component.
* Props can be of any type: strings, numbers, arrays, objects, functions, or even other React components.

## Passing Props

Props are passed to a component as attributes in JSX.

```
function Greeting(props) {
  return <h1>Hello, {props.name}!</h1>;
}

function App() {
  return <Greeting name="John" />;
}
```

## Accessing Props

Props are passed as an object to the component function or class. You can access them using props in functional components or this.props in class components.

```
// Functional component
function Greeting(props) {
  return <h1>Hello, {props.name}!</h1>;
}

// Class component
class Greeting extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}!</h1>;
  }
}
```

## Destructuring Props

To make your code cleaner, you can use destructuring to extract props directly in the function parameters.

```
function UserCard({ name, age, location }) {
  return (
    <div>
      <h2>{name}</h2>
      <p>Age: {age}</p>
      <p>Location: {location}</p>
    </div>
  );
}
```

## Passing Functions as Props

You can pass functions as props to allow child components to communicate with parent components.

```
function Button(props) {
  return <button onClick={props.onClick}>Click Me</button>;
}

function App() {
  const handleClick = () => {
    alert('Button clicked!');
  };

  return <Button onClick={handleClick} />;
}
```

##  Default Props

You can define default values for props using the defaultProps property. This is useful when a prop is not provided.

```
function Greeting(props) {
  return <h1>Hello, {props.name}!</h1>;
}

Greeting.defaultProps = {
  name: "Guest",
};

function App() {
  return (
    <div>
      <Greeting name="John" /> {/* Output: Hello, John! */}
      <Greeting /> {/* Output: Hello, Guest! */}
    </div>
  );
}
```

## Prop Types (Type Checking)

React provides a way to validate the types of props using the prop-types library. This helps catch bugs and ensures that components receive the correct data types.

```
import PropTypes from 'prop-types';

function Greeting(props) {
  return <h1>Hello, {props.name}!</h1>;
}

Greeting.propTypes = {
  name: PropTypes.string.isRequired,
};

function App() {
  return <Greeting name="John" />;
}
```

## Children Prop

The children prop is a special prop that allows you to pass content between the opening and closing tags of a component.

```
function Card(props) {
  return (
    <div className="card">
      {props.children}
    </div>
  );
}

function App() {
  return (
    <Card>
      <h2>Title</h2>
      <p>Description</p>
    </Card>
  );
}  
```

