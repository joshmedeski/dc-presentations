+++
title = "Python Dictionaries"
outputs = ["Reveal"]
+++

# Python Dictionaries

---

## Overview

- What the dictionary data type is
- Getting data from a dictionary
- How to manipulate a dictionary
- How to loop through a dictionary

---

## What the dictionary data type is

> A dictionary is a collection which is unordered, changeable and indexed. In Python dictionaries are written with curly brackets, and they have keys and values.
>
> - [w3schools](https://www.w3schools.com/python/python_dictionaries.asp)

---

## Sample Dictionary

```py
{
    'key': 'value'
}
```

```py
{
    'name': 'John',
    'age': 50,
    'isRegistered': True
}
```

\*Note: the value can be any data type!

---

## What is a dictionary good for?

- Storing complex data sets
- Creating structure for complex data
- Grouping related data for a single entry

---

## Named Indexes

```py
names = ['John', 'Eric', 'Micah']
names[0]
```

```py
person = {
    'name': 'John',
    'age': 50,
    'isRegistered': True
}
person['name']
person.get('name')
```

---

## Manipulating a Dictionary

---

## Changing Values

```py
person = { 'name': 'Jane' }
person['name'] = 'Joy'
person['age'] = 65
```

---

## Deleting Values

```py
person = { 'name': 'Joy', age: 65 }
person.pop('age')
del person['age']
person.clear()
```

---

## Array of Dictionaries

```py
people = [
    { "name": "John", "age": 55 },
    { "name": "Micah", "age": 40 },
    { "name": "Eric", "age": 55 }
]
```

---

## Nesting

```py
family = {
    surname: 'Smith',
    address: '17 Cherry Tree Lane',
    members: [
        { name: 'John', relationship: 'Father'},
        { name: 'Jane', relationship: 'Mother'},
        { name: 'Suzie', relationship: 'Daughter'},
        { name: 'Barry', relationship: 'Son'},
    ]
}
```

---

# Loops

```py
for key in person:
    # Code
for value in person.values():
    # Code
for key, value in person.items():
    # Code
```

\*But why loop through a dictionary?

---

## Dictionary Summary

- What the dictionary data type is
- Getting data from a dictionary
- How to manipulate a dictionary
- How to loop through a dictionary

---
