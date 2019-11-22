+++
title = "Combine Reducers"
outputs = ["Reveal"]
+++

# Combine Reducers

---

# Overview

- Creating Separate Reducers
- Combine Reducers
- Create Store

---

## Creating Separate Reducers

---

### Create Todo Reducer

```js
export default function todos(state = [], action) {
  switch (action.type) {
    case "ADD_TODO":
      return state.concat([action.text]);
    default:
      return state;
  }
}
```

---

### Create Counter Reducer

```js
export default function counter(state = 0, action) {
  switch (action.type) {
    case "INCREMENT":
      return state + 1;
    case "DECREMENT":
      return state - 1;
    default:
      return state;
  }
}
```

---

### Combine Reducers

```js
import { combineReducers } from "redux";
import todos from "./todos";
import counter from "./counter";

export default combineReducers({
  todos: todos,
  counter: counter
});
```

---

#### Create Store

```js
import { createStore } from "redux";
// combined reducer
import reducer from "./reducers/index";

const store = createStore(reducer);
```

---

# Summary

- Creating Separate Reducers
- Combine Reducers
- Create Store
