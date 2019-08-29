+++
title = "Python Lists"
outputs = ["Reveal"]
+++

# Python Lists

---

## Overview

- What are lists
- Indexing lists
- How to manipulate lists
- How to loop through lists

---

## What are lists?

Data type for listing multiple values in one piece of data.

```py
['Josh', 'Eric', 'Haley', 'Jason', 'Veronica', 'Azam']
```

---

## What are lists good for?

- Grouping related data
- Combing data that you want to loop
- Finding differences or similarities

---

## Indexing

Zero indexing arrays

```py
names = ['Josh', 'Eric', 'Haley', 'Jason', 'Veronica', 'Azam']
# 0, 1, 2, 3, 4, 5
names[0]
names[4]
names[2] = 'John'
```

---

## Getting the length

```py
names = ['Josh', 'Eric', 'Haley', 'Jason', 'Veronica', 'Azam']
len(names)
```

---

## Manipulating lists

---

## Appending

```py
names = ['Josh', 'Eric', 'Haley', 'Jason', 'Veronica', 'Azam']
names.append('Micah')
```

---

## Slicing

```py
s[i:j]
```

Slice of s from i up to j is replaced by the contents of the iterable t.

```py
names = ['Josh', 'Eric', 'Haley', 'Jason', 'Veronica', 'Azam']
names[0:2]
names[3:5]
```

---

### More Ways to Manipulate Lists

- list.insert(3, item) - inserts item at specified location
- list.extend([3, 4, 5]) - appends all items in given list to this list
- list.pop() - removes an item from the end of the list

---

### More Ways to Manipulate Lists

- list.sort() - sorts the list
- list.copy() - returns a new copy of the list
- list.clear() - removes all items from the list

---

## Strings as lists

```py
my_string = 'Hello'
my_string[0]
len(my_string)
my_string[1:4]
```

---

## Multidimensional lists

```py
matrix = [[2,6],[6,2],[8,2],[5,12]]
print(x[2])
print(x[2][1])
```

---

# Loops

---

## Review: While

```py
iteration = 0
while iteration < 10:
    print(f'Printing item {iteration}')
    iteration += 1
```

- Set up the index
- Check the condition
- Increment the index

---

## For Loops

```py
names = ['Josh', 'Eric', 'Haley', 'Jason', 'Veronica', 'Azam']
for name in names:
    print(f'Hello, {name}')
```

---

## Range

```py
range(10) # 1-9
range(10,20)
range(10, 20, 2)
```

```py
for number in range(0, 10):
    print(number)
```

## Recap

- What are lists
- Indexing lists
- How to manipulate lists
- How to loop through lists

---

# Q&A

---
