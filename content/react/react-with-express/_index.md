+++
title = "React with Express"
outputs = ["Reveal"]
+++

# React with Express

Using React and Express together (full-stack)

---

## Create React App

```sh
$ npx create-react-app client
```

---

## Create Express App

```sh
$ npx express-generator --no-view --git server
$ cd server
$ npm install
```

---

## Changing Port in Express

```js
// ./server/bin/www
var port = normalizePort(process.env.PORT || "3001");
```

---

### Setting Up Express Proxy

This will allow the React app to make requests that connect to the Express app.

```json
// ./client/package.json
{
  "proxy": "http://localhost:3001"
}
```

---

### Sample JSON Response

```js
// ./server/routes/users.js
router.get("/", function(req, res, next) {
  res.json(["Josh", "Summer", "Angelo", "Steven"]);
});
```

---

## Running Express & App

```sh
$ cd server
$ npm start
```

```sh
$ cd client
$ npm start
```

---

## Simple Component

```js
// Create a <Users /> component
componentDidMount() {
    fetch("/users")
      .then(res => res.json())
      .then(users => this.setState({ users }));
  }
```

---

### JSX

```jsx
<ul>
{
  this.state.users.map((user, index) => {
    return <li key={index}>{user}</li>
  });
}
</ul>
```
