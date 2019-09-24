+++
title = "Python Classes"
outputs = ["Reveal"]
+++

# Python Classes

---

## Classes Overview

- What are classes?
- How to create classes
- How to use classes

---

## Creating a Class

```py
class User:
  def __init__(self, first_name, age):
    self.first_name = first_name
    self.age = age

user1 = User("John", 36)
print(user1.first_name)
print(user1.age)
```

---

## Functions in Classes

```py
class Math:
    # Returns the provided number doubled
    def double(x):
        return x * 2

math = Math()
math.double(5)
```

---

## Classes Summary

- What are classes?
- How to create classes
- How to use classes

---
