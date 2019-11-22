+++
title = "Redux Thunk Middleware"
outputs = ["Reveal"]
+++

# Redux Thunk Middleware

---

## Overview

- What is middleware
- Creating actions
- Creating thunk action
- Put it all together

---

### What is middleware?

It provides a third-party extension point between dispatching an action, and the moment it reaches the reducer. People use Redux middleware for logging, crash reporting, talking to an asynchronous API, routing, and more.

[Redux docs on middleware](https://redux.js.org/advanced/middleware)

---

![redux-diagram](./redux-diagram.gif)

---

### What is thunk?

A thunk is another word for a function. But it’s not just any old function. It’s a special (and uncommon) name for a function that’s returned by another. Like this:

```js
function wrapper_function() {
  // this one is a "thunk" because it defers work for later:
  return function thunk() {
    // it can be named, or anonymous
    console.log("do stuff now");
  };
}
```

Article: [What the heck is a 'thunk'?](https://daveceddia.com/what-is-a-thunk/)

---

### Installing thunk

```sh
npm install redux-thunk
```

[reduxjs/redux-thunk](https://github.com/reduxjs/redux-thunk)

---

### Applying middleware

```js
import thunk from "redux-thunk";
const store = createStore(rootReducer, applyMiddleware(thunk));
```

---

### Creating actions

In order to track the status of the asynchronous process, create an action for each step along the way.

```js
export const FETCH_PRODUCTS_BEGIN = "FETCH_PRODUCTS_BEGIN";
export const FETCH_PRODUCTS_SUCCESS = "FETCH_PRODUCTS_SUCCESS";
export const FETCH_PRODUCTS_FAILURE = "FETCH_PRODUCTS_FAILURE";

export const fetchProductsBegin = () => ({ type: FETCH_PRODUCTS_BEGIN });

export const fetchProductsSuccess = products => ({
  type: FETCH_PRODUCTS_SUCCESS,
  payload: { products }
});

export const fetchProductsFailure = error => ({
  type: FETCH_PRODUCTS_FAILURE,
  payload: { error }
});
```

---

### The Reducer

```js
export default function productReducer(state = initialState, action) {
  switch (action.type) {
    case FETCH_PRODUCTS_BEGIN:
      return {
        ...state,
        loading: true, // start loading
        error: null // reset error
      };
    case FETCH_PRODUCTS_SUCCESS:
      return {
        ...state,
        loading: false, // stop loading
        items: action.payload.products // response from api
      };
    case FETCH_PRODUCTS_FAILURE:
      return {
        ...state,
        loading: false, // stop loading
        error: action.payload.error, // response from api error
        items: []
      };
    default:
      return state;
  }
}
```

---

### Creating thunk action

```js
export function fetchProducts() {
  return async dispatch => {
    dispatch(fetchProductsBegin());
    try {
      const json = await fakeGetProducts(); // api call
      dispatch(fetchProductsSuccess(json.products));
      return json.products;
    } catch (error) {
      return dispatch(fetchProductsFailure(error));
    }
  };
}
```

---

### Calling the thunk middleware in React

When we `connect()` the React component with React, you can use the `props.dispatch` function to call actions.

```js
componentDidMount() {
  // load products on page load
  this.props.dispatch(fetchProducts());
}
```

---

### Rendering the app

```js
render() {
  const { error, loading, products } = this.props;

  if (error) { // show error message
    return <div>Error! {error.message}</div>;
  }

  if (loading) { // show loading state
    return <div>Loading...</div>;
  }

  return (
    <ul> {/* show products on load */}
      {products.map(product =>
        <li key={product.id}>{product.name}</li>
      )}
    </ul>
  );
}
```

---

![redux-diagram](./redux-diagram.gif)
