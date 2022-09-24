# My Portfolio Website

React project to demonstrate use of react in web development. First benefit is using JSX.

## Components

React uses component approach to Design process. It basically helps to create seperation of concerns. React uses Two type of Components:

1. Functional Components
2. Class Components

### Functional Components

```js
function Hello(){
  return <h1>Hello, World.</h2>;
}
```

**Rendering react component**

```js
const el = <Hello />;

ReactDOM.render(el, document.getElementById("root"));
```

> Note: Functional Components name is capitalized.

### Class Components

We use class approach when components are more complicated.

--> It needs to extend React.Component class.

```js
class Hello extends React.Component {
  render() {
    return <h1>Hello World.</h1>;
  }
}
```

## Props

Props are arguments that functional component accepts.
Props represents the object type.

## State

State are objects that allows to manage and change components data in class components.

To change state of the componentm we use **setState**.

```js
  ...
  this.state = {
    count: 0
  }

  increase = () => {
    this.setState(
      {
        count: this.state.count +1
      }
    );
  }
  ...
```

## Props vs State

- Props are read only and cannot be modified.
- State can be modified using `setState()` method. Using this method results in re-rendering the component affected.

## Hooks

Hooks allow to use State inside functional components.

```js
// needed imports for hooks.
import React, { useState } from "react";
```

Eg: A Hook Example-

```js
function Hello() {
  // [] brackets is array destructuring.
  // assigns name to current state value. setName function
  // allows to change the state.`
  const [name, setName] = useState("Sijan");

  // to change name
  function changename() {
    setName("Season");
  }

  return (
    <div>
      <h1>Hello {name}</h1>
      <button onClick={changename}> Change Name </button>
    </div>
  );
}
```

## Lifecycle Management

Life cycles of components are: mounted, updated and unmounted.

Mounting: component is rendered in the page. `componentDidMount()`

Unmounting: component is removed from the page. `componentWillUnmount()`

Updated: component is called in the page. `componentDidUpdate()`

> Note: with functional components, there is special hook useEffect to make lifecycle methods available.

```js
// needed imports
import React, {useState, useEffect} from 'react';

function Count() {
  const [count, setCount] = useState(0);

  // It is same as componentDidUpdate()
  // and componentDidMount()
  useEffect(() => {
    alert(count);
  });
  ...
  // It is same as componentDidUpdate()
  useEffect(
    ()=> {
      //dosomething
    },[count]
  );
  ...
}
```

## Event Handling

Similar to handling events in the DOM.

Use camelCase Syntax for event name | event handler needs to be passed in curly braces.

```html
<button onClick="{handleClick}">Button</button>
```
