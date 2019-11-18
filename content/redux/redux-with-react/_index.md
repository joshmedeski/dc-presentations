+++
title = "Redux with React"
outputs = ["Reveal"]
+++

# Redux with React

---

## Overview

- Installing Redux
- Creating action types
- Creating actions
- Creating a reducer
- Creating store
- Using a \<Provider\>
- Mapping state to props
- Mapping dispatch to props
- Pass components inside provider

---

### Installing Redux

```sh
$ npm install redux react-redux
```

---

### Creating action types

```js
// ./redux/actionTypes.js
export const INCREMENT = "INCREMENT";
export const INCREMENT_IF_ODD = "INCREMENT_IF_ODD";
export const DECREMENT = "DECREMENT";
```

---

### Creating actions

```js
// ./redux/actions.js
import { INCREMENT, DECREMENT, INCREMENT_IF_ODD } from "./actionTypes";

export const increment = () => ({ type: INCREMENT });
export const decrement = () => ({ type: DECREMENT });
export const incrementIfOdd = () => ({ type: INCREMENT_IF_ODD });
```

---

### Creating a reducer

```js
import { INCREMENT, DECREMENT, INCREMENT_IF_ODD } from "./actionTypes";

export default function reducer(state = 0, action) {
  switch (action.type) {
    case INCREMENT:
      return state + 1;
    case DECREMENT:
      return state - 1;
    case INCREMENT_IF_ODD:
      return state % 2 !== 0 ? state + 1 : state;
    default:
      return state;
  }
}
```

---

### Creating store

```js
import { createStore } from "redux";
import reducer from "./reducer";

export default createStore(reducer);
```

---

### Using a \<Provider\>

```js
import React from "react";
import { Provider } from "react-redux";
import store from "./redux/store";

export default function App() {
  return (
    <Provider store={store}>
      <h1>Redux with React Exercise - Counter</h1>
    </Provider>
  );
}
```

---

### Mapping state to props

```js
import React from "react";
import { connect } from "react-redux";

const Count = ({ count }) => {
  return <h2>Clicked: {count} times</h2>;
};

const mapStateToProps = state => {
  return { count: state };
};

export default connect(mapStateToProps)(Count);
```

---

### Mapping dispatch to props

```js
import React from "react";
import { connect } from "react-redux";
import { increment } from "../redux/actions";

const IncrementButton = ({ increment }) => {
  return (
    <button type="button" onClick={increment}>
      Increment
    </button>
  );
};

const mapDispatchToProps = { increment };

export default connect(null, mapDispatchToProps)(IncrementButton);
```

---

### Pass components inside provider

```js
<Provider store={store}>
  <h1>Redux with React Exercise - Counter</h1>
  <Count />
  <IncrementButton />
</Provider>
```

---

## Summary

- Installing Redux
- Creating action types
- Creating actions
- Creating a reducer
- Creating store
- Using a \<Provider\>
- Mapping state to props
- Mapping dispatch to props
- Pass components inside provider
