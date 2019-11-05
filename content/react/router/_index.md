+++
title = "React Router"
outputs = ["Reveal"]
+++

# React Router

---

## NPM Package

https://www.npmjs.com/package/react-router-dom

```sh
$ npm i react-router-dom
```

---

## Importing

```js
import { BrowserRouter as Router, Switch, Route } from "react-router-dom";
```

<small>\*Notice destructuring with `{}`</small>

---

## Router Component

```jsx
<Router>
  <Switch>
    <Route path="/">
      <HomePage />
    </Route>
  </Switch>
</Router>
```

---

## Basic Route

```js
<Route path="/">
  <HomePage />
</Route>
```

---

## Route with Param

```js
<Route path="/books/:id">
  <BookPage />
</Route>
```

---

## Using Param Values

```js
import { useParams } from "react-router-dom";

export default function BookPage() {
  // get value from route (destructuring assignment again)
  let { id } = useParams();
  return <h3>Book ID: {id}</h3>;
}
```

---

## Catch all

```jsx
<Route>
  <PageNotFound />
</Route>
```

Order matters, make this last

---

### Putting It All Together

```jsx
<Router>
  <Switch>
    {/* Basic route */}
    <Route path="/">
      <Page />
    </Route>
    {/* Route with param */}
    <Route path="/books/:id">
      <BookPage />
    </Route>
    {/* Catch all (order matters, make this last) */}
    <Route>
      <PageNotFound />
    </Route>
  </Switch>
</Router>
```

---

## Linking to Pages

```js
import { Link } from "react-router-dom";
```

```js
<Link to="/">Home</Link>
<Link to="/books/archive">Archive</Link>
```

---

# Resources

- [GitHub Repo - React Router](https://github.com/ReactTraining/react-router)
- [React Router Training](https://reacttraining.com/react-router/web/example/basic)
