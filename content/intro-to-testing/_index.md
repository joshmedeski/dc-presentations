+++
title = "Intro to Testing"
outputs = ["Reveal"]
+++

# Intro to Testing

---

## What is Testing?

To examine that the code written has the expected functionality and output expected by the developer and product owner.

---

## Why Test?

-

---

### Manual Testing

- Done by hand (good ol' mouse & keyboard)
- Doesn't require coding skills
- Is done before automatic testing
- Helps discover bugs

---

### Automatic Testing

- Tests written out with code and executed by a computer
- Repeatable and automated
- Requires programming skills
- Can be done many ways (unit, integration, etc...)

---

### Examples of Automatic Testing

- Unit testing
- Integration testing
- End-to-end testing

There are 100+ types of testing, here is a [list of more](https://www.guru99.com/types-of-software-testing.html).

---

### Test Driven Development (TDD)

- Write the tests first (the tests will fail)
- Write the code to make the tests pass
- Deploy when all tests have passed

---

### Behavior Driven Development (BDD)

- Define the user's behavior first
- Approve the BDD tests with the product owner
- Write the code to make the tests pass
- Deploy when all tests have pass

---

## Simple Unit Test Example

```js
function double(numberToDouble) {
  return numberToDouble * 2;
}
var assert = require("chai").assert;
expect(double(2)).to.equal(4);
```

---

## What can you test?

- Modules (functions)
- Routes (API)
- User Interface (UI)

---

## Some Testing Terms

- Code Coverage: What percentage of the codebase is executed by tests
- Happy Path: The simplest, most expected, outcome for a feature
- Quality Assurance (QA): a designated role for managing and creating tests (either manual or automatic) for a software team

---

## Recommended Frameworks

- [Jest](https://jestjs.io/) for unit testing
- [Cypress](https://www.cypress.io/) for end-to-end testing
