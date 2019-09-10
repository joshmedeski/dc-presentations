+++
title = "Responsive Design"
outputs = ["Reveal"]
+++

# Responsive Design

---

### Responsive Design Overview

- What it is
- Mobile first
- Viewport
- Fluid layout
- Media queries
- Responsive Images
- Exercise

---

### What is responsive design?

Design approach where design and development respond to the user's behavior and environment based on screen size, platform and orientation.

---

## Other design approaches

- Adaptive: User Agent Detection normally server side
- Mobile Dedicated

---

## Mobile first

Starting the design process with mobile.

---

## Viewport

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

---

## Media queries

```css
@media not|only mediatype and (mediafeature and|or|not mediafeature) {
}
```

```css
@media screen and (min-width: 800px) {
}
```

[media rule](https://www.w3schools.com/cssref/css3_pr_mediaquery.asp)

---

## Responsive Images

```css
img {
  max-width: 100%;
  height: auto;
}
```

---

### Creating Mobile First Layout

Let's build a layout together.

---

### Responsive Design Summary

- What it is
- Mobile first
- Viewport
- Fluid layout
- Media queries
- Responsive Images
- Exercise
