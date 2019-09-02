+++
title = "Python 101"
outputs = ["Reveal"]
+++

# Python 101

---

## Overview

- What is Python?
- Installing & Using Python
- User Input
- Variables
- Printing
- Basic Data Types (string, integer, float, float, boolean)
- Calculating & Comparison
- Conditions
- Loops

---

## What is Python?

- Created in the 1980s
- Named after "Monty Python's Flying Circus"
- Version 1.0 (first released in 1991)
- Version 2.0 (October 16, 2000)
- Version 3.0 (December 3, 2008)

---

## Features

- Easy code readability
- Object-oriented
- Dynamically typed
- Garbage collected
- "batteries included" language (standard library)

---

## Installing Python

```sh
$ brew install python
```

---

## REPL

What is REPL? REPL is the language shell. Its short for Read, Eval, Print and Loop. The process is:

- Read: take user input
- Eval: evaluate the input
- Print: shows the output to the user
- Loop: repeat

---

## Running Python Files

```sh
$ python3 sample.py
```

---

## User Input

```
input("How old are you?")
```

---

## Variables

Reserved memory locations to store values.

```py
identifier = expression
legal_age = 21
user_age = input('How old are you? ')
```

(Note the **snake_case**)

---

## Printing

```py
print('Hello World')
```

```py
age = 21
print(f'I am {age}')
```

---

## Data Types

> Tells the compiler or interpreter how the programmer intends to use the data
>
> - [Wikipedia](https://en.wikipedia.org/wiki/Data_type)

---

## String

```py
'String'
'Haikus are easy.\nBut sometimes they don\'t make sense.\n Refrigerator.'
name = "Josh Medeski"
```

---

## Concatenating Strings

```py
'hello' + 'world'
```

---

## Integer (int)

Any whole number

```py
number_of_employees = 53
bottles_of_beer_on_the_wall = 99
```

---

## Float

Any number with a decimal point.

```py
pi = 3.141592
tax = 8.25
tax_percentage = 0.0825
```

---

### Converting Inputs to Integers

```py
year_born = int(input('What year were you born? '));
print(f'You were born in {year_born}')
```

---

## Calculating

| Symbol | Operation      |
| ------ | -------------- |
| +      | Addition       |
| -      | Subtraction    |
| \*     | Multiplication |
| /      | Division       |

---

### Calculating Examples

```py
year_born = int(input('What year were you born? '));
years_ago = 2019 - year_born
print(f'You were born {years_ago} years ago')
```

---

### Advanced Examples

```py
5 + 30 * 20 / 10
```

```py
((5 + 30) * 20) / 10
```

---

## Comparison

| Symbol | Meaning                  |
| ------ | ------------------------ |
| >      | greater than             |
| <      | less than                |
| >=     | greater than or equal to |
| <=     | less than or equal to    |
| ==     | equal to                 |
| !=     | not equal to             |

---

## Comparison Examples

- 5 > 4 (greater than) - true
- 9 < 5 (less than) - false
- 7 >= 9 (greater than or equal to) - false
- 4 <= 8 (less than or equal to) - true

---

## Boolean

A binary value, either `True` or `False`

```py
is_nice = True
is_allowed_to_drive = False
```

Note: False, 0, None, "", and empty collections like [] and {} are falsey otherwise it's true

---

## Conditions

```py
if condition:
    # execute statement block
```

```py
age = 30
if age >= 21:
    print('Allowed to drink')
```

---

## Else Condition

```py
age = 18
if age >= 21:
    print('Allowed to drink')
else:
    print('This person is underage!')
```

---

## Elif Conditions

```py
age = 15
if age >= 16:
    print('Allowed to drive')
elif age == 15:
    print('Allowed to get a permit')
else:
    print('Not allowed to drive')
```

---

## Loops

```py
iteration = 0
while iteration > 10:
    print(f'This is iteration number {iteration}')
    iteration += 1
print("Finished")
```

---

## Loop Example

```py
answer = ''
while answer != 'when':
  answer = input('Say when: ')
  answer = answer.lower()
print("Cheese")
```

```py
while True:
  answer = input('Say when: ')
  if answer.lower() == 'when':
    break
print("Cheese")
```

---

## Python 101 Summary

- What is Python?
- Installing & Using Python
- User Input
- Variables
- Printing
- Basic Data Types (string, integer, float, float, boolean)
- Calculating & Comparison
- Conditions
- Loops

---
