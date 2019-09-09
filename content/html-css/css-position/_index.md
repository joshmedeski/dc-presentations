+++
title = "CSS Position"
outputs = ["Reveal"]
+++

# CSS Position

---

## CSS Position Overview

How to positions HTML using CSS:

- `static`, `relative`, `absolute`, `fixed`
- `top`, `bottom`, `left`, `right`
- `z-index`

---

### `position: static`

The `static` position is the default. Top down, left to right.

---

### `position: relative`

Positions the element relative to it's default position.

---

### `top`, `bottom`, `left`, `right`

Positions the element starting from the given property.

```css
top: 50px;
bottom: 0;
left: 2em;
right: 1vw;
```

---

### `position: absolute`

Positions the element from the body, or the closest `position: relative;` parent.

---

### `position: fixed`

Positions the element to the browser window and keeps it fixed in that place (even when scrolling).

---

### `z-index`

When elements overlap, you can use the `z-index` property to
control which element is on top of another.

Note: The higher the number value, the closer it is to the front of the view

---

## CSS Position Summary

How to positions HTML using CSS:

- `static`, `relative`, `absolute`, `fixed`
- `top`, `bottom`, `left`, `right`
- `z-index`
