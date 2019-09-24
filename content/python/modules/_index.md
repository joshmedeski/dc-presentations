+++
title = "Python Modules"
outputs = ["Reveal"]
+++

# Python Modules

---

## Modules Overview

- What are modules?
- How to create modules
- How to import modules

---

## What is a module?

A piece of code that accomplishes specific functionality.

---

### Single Responsibility Principle

> The **single responsibility principle** is a computer programming principle that states that every module, class, or function] should have responsibility over a single part of the functionality provided by the software
>
> - [Wikipedia](https://en.wikipedia.org/wiki/Single_responsibility_principle)

---

## Importing Modules

```py
import math # standard library
math.floor(x)
```

---

## Importing specific functions

```py
from math import floor
floor(x)
```

---

## Importing all functions

```py
from math import *
floor(x)
```

---

## Alias imports

```py
from math as m
m.floor(x)
```

---

## Importing Custom Module

```py
# custom.py
def special_command():
    pass
```

```py
# main.py
import custom
custom.special_command()
```

---

## Custom Module

```py
# custom.py
def special_command():
    pass
```

```py
# main.py
import custom_module
custom_module.special_command()
```

---

## Modules Summary

- What are modules?
- How to import modules
- How to create modules

---
