+++
title = "JSON & AJAX"
outputs = ["Reveal"]
+++

# JSON & AJAX

---

# Overview

- What is JSON?
- How to use JSON
- What is AJAX?
- How to make AJAX requests

---

## What is JSON?

JSON (JavaScript Object Notation) is a lightweight data-interchange format. It is easy for humans to read and write. It is easy for machines to parse and generate.

[json.org](http://json.org/)

---

## JSON Sample

```json
{
  "first_name": "Josh",
  "last_name": "Medeski",
  "from": "Houston"
}
```

---

### How can we most efficiently transfer data?

---

## Stringify

```js
var person = {
  first_name: "Josh",
  last_name: "Medeski",
  from: "Houston"
};
JSON.stringify(person);
```

---

## Parse

```js
var personString = "{"first_name":"Josh","last_name":"Medeski","from":"Houston"}"
JSON.parse(personString)
```

---

## What is AJAX?

**A**synchronous **J**avaScript **A**nd **X**ML

- AJAX is not a programming language.
- AJAX just uses a combination of:
  - A browser built-in XMLHttpRequest object (to request data from a web server)
  - JavaScript and HTML DOM (to display or use the data)

[Source: w3schools](https://www.w3schools.com/xml/ajax_intro.asp)

---

## How AJAX works

![how ajax works](./how-ajax-works.gif)

---

### How to make AJAX requests

```js
new XMLHttpRequest(); // vanilla
$.ajax(); // jQuery
```

---
