+++
title = "Python Function"
outputs = ["Reveal"]
+++

# Python Functions

---

## Functions Overview

- What are functions?
- How to create functions
- How to return data
- How to call functions
- Lambda functions
- Composing functions

---

## What are functions?

---

## Mathmatical Functions

- x^2 (squared)
- y=mx+b

Input -> Output

---

## Why use functions?

- Never write multiple copies of the same code (DRY vs WET)
- Reusable chunks of code
- Create sub routines or programs within a main program
- Break up application into smaller functionality

---

### Examples of "real world" functions

- Converting temperature
- Calculate tax for shopping cart
- Add tax to a purchase
- Indicate strength of a password

---

## How to write functions

```py
def function_name(param1, param2, param3):
    pass
```

```py
def double(x):
  print(f'{x} doubled is {x * 2}')

double(4)
```

---

## Building Functions

```py
def getGroceries():
    print('milk')
    print('flour')
    print('sugar')
    print('butter')
    print()
```

- Acts a s sub program
- When you run your program, nothing will happen
- code will not execute by itself.
- Main part of code has to do something to execute this functions

---

### Calling a function

```py
def getGroceries():
    print('milk')
    print('flour')
    print('sugar')
    print('butter')
    print()

getGroceries()
```

- getGroceries() executes the function
- Executing a functions is = "Calling a function"
- Can make several calls to the same function

---

### Combining Functions

```py
def separateRuns():
    print('******************')
    print() # blank line

def getGroceries():
    print('milk')
    print('flour')
    print('sugar')
    print('butter')
    separateRuns()

getGroceries()
getGroceries()
```

---

## How to return data

```py
def double(x):
  print(f'{x} doubled is {x * 2}')

double(4)
```

```py
def double(x):
    return x * 2

number_to_double = input('What number do you want to double? ')
number_doubled = double(number_to_double)
print(f'{number_to_double} doubled is {number_doubled}')
```

---

## Functions Summary

- What are functions?
- How to create functions
- How to call functions
- How to return data
- Composing functions

---
