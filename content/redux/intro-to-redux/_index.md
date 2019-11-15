+++
title = "Intro to Redux"
outputs = ["Reveal"]
+++

# Intro to Redux

---

## Overview

- What is Redux
- Core Concepts
- Three Principles
- Using Redux

---

## What is Redux

> Redux is a predictable state container for JavaScript apps.

---

## The Issue without Redux

We're mixing two concepts: **mutation** and **asynchronicity** (like Mentos & Coke).

Redux attempts to make state mutations predictable.

---

## Core Concepts

Imagine your app's state as a plain JS object.

```js
{
  todos: [
    {
      text: "Eat food",
      completed: true
    },
    {
      text: "Exercise",
      completed: false
    }
  ],
  visibilityFilter: "SHOW_COMPLETED"
};
```

---

## No Mutations

We will not directly change any of the state's values arbitrarily, because it can cause bugs that are hard-to-recreate.

~~state.visibilityFilter = 'SHOW_ALL'~~

---

## Dispatching Actions

To update the state, you dispatch an action. It's a plain JS object describing what to do and the new data.

```js
{ type: 'ADD_TODO', text: 'Go to swimming pool' }
{ type: 'TOGGLE_TODO', index: 1 }
{ type: 'SET_VISIBILITY_FILTER', filter: 'SHOW_ALL' }
```

---

## Reducers

Takes state and action as arguments, and returns the next state of the app.

```js
function visibilityFilter(state = "SHOW_ALL", action) {
  if (action.type === "SET_VISIBILITY_FILTER") {
    return action.filter;
  } else {
    return state;
  }
}
```

---

Reducers can be separated into separate functions for each area of state.

```js
function todos(state = [], action) {
  switch (action.type) {
    case "ADD_TODO":
      return state.concat([{ text: action.text, completed: false }]);
    case "TOGGLE_TODO":
      return state.map((todo, index) =>
        action.index === index
          ? { text: todo.text, completed: !todo.completed }
          : todo
      );
    default:
      return state;
  }
}
```

---

## Combing Reducers

Finally, we create a root reducer that manages all of the state of the app.

```js
function todoApp(state = {}, action) {
  return {
    todos: todos(state.todos, action),
    visibilityFilter: visibilityFilter(state.visibilityFilter, action)
  };
}
```

---

## Three Principles

- Single source of truth
- State is read-only
- Changes are made with pure functions

---

#### Single source of truth

The state of your whole application is stored in an object tree within a single store.

```js
console.log(store.getState());

/* Prints
{
  todos: [
    {
      text: 'Consider using Redux',
      completed: true,
    },
    {
      text: 'Keep all state in a single tree',
      completed: false
    }
  ],
  visibilityFilter: 'SHOW_ALL'
}
*/
```

---

### State is read-only

The only way to change the state is to emit an action, an object describing what happened.

```js
store.dispatch({
  type: "COMPLETE_TODO",
  index: 1
});

store.dispatch({
  type: "SET_VISIBILITY_FILTER",
  filter: "SHOW_COMPLETED"
});
```

---

#### Changes are made with pure functions

To specify how the state tree is transformed by actions, you write pure reducers.

```js
function todos(state = [], action) {
  switch (action.type) {
    case "ADD_TODO":
      return [
        ...state,
        {
          text: action.text,
          completed: false
        }
      ];
    default:
      return state;
  }
}
```

---

### Using Redux

- Writing reducer function
- Creating a store
- Dispatching actions
- Getting state
- Subscribe to changes

---

### Writing reducer function

A reducing function that returns the next state tree, given the current state tree and an action to handle (plain javascript)

```js
function reducer(state = [], action) {
  switch (action.type) {
    case "ADD_TODO":
      return [
        ...state,
        {
          text: action.text,
          completed: false
        }
      ];
    default:
      return state;
  }
}
```

---

## Creating a store

Creates a Redux store that holds the complete state tree of your app. There should only be a single store in your app.

```js
var store = Redux.createStore(reducer);
```

---

## Dispatching actions

Dispatches an action. This is the only way to trigger a state change.

```js
store.dispatch({
  type: "COMPLETE_TODO",
  index: 1
});
```

---

## Getting state

Returns the current state tree of your application. It is equal to the last value returned by the store's reducer.

```js
store.getState();
```

---

## Subscribe to changes

Adds a change listener. The 'listener' function will be called any time an action is dispatched.

```js
store.subscribe(listener);
```

---

## Summary

- What is Redux
- Core Concepts
- Three Principles
- Using Redux
