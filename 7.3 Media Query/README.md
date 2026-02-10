# CSS Media Queries – Background Color Demo

This README explains how the given HTML and CSS file uses **media queries** to change the background color of the page based on **screen width (viewport size)**.

This exercise demonstrates the fundamentals of **responsive design** using CSS only.

---

## Purpose of This File

The goal of this practice is to:

* Understand how `@media` queries work
* Learn how different screen sizes are detected
* Visually verify breakpoints using background colors
* Practice writing multiple media queries correctly

When the browser window is resized, the background color changes according to the device width.

---

## Viewport Meta Tag (Very Important)

```html
<meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1" />
```

### Why this matters

* Ensures proper scaling on mobile devices
* Makes media queries work correctly on phones and tablets
* Without this tag, mobile browsers may render the page at desktop width

---

## Default CSS Rule

```css
body {
  background-color: aquamarine;
}
```

* Acts as a **fallback color**
* Applies when no media query condition is matched
* Useful for debugging and testing

---

## Media Query Breakdown

### 1. Mobile Devices (319px – 480px)

```css
@media (min-width: 319px) and (max-width: 480px) {
  body {
    background-color: lightsalmon;
  }
}
```

* Targets small mobile devices
* Background color: **lightsalmon**
* Commonly used for phones

---

### 2. Tablets and iPads (481px – 1200px)

```css
@media (min-width: 481px) and (max-width: 1200px) {
  body {
    background-color: powderblue;
  }
}
```

* Targets tablets and medium-sized screens
* Background color: **powderblue**

---

### 3. Laptops (1201px – 1600px)

```css
@media (min-width: 1201px) and (max-width: 1600px) {
  body {
    background-color: limegreen;
  }
}
```

* Targets laptops and smaller desktops
* Background color: **limegreen**

---

### 4. Large Desktops (1601px and above)

```css
@media (min-width: 1601px) {
  body {
    background-color: seagreen;
  }
}
```

* Targets large desktop monitors
* Background color: **seagreen**

---

## How Media Queries Work Here

* CSS checks **all media queries continuously** as the browser resizes
* When a condition becomes true, its styles are applied
* Only one background color applies at a time
* If multiple queries could match, the **last matching rule wins**

---

## Visual Testing Instructions

To test this file:

1. Open the HTML file in a browser
2. Resize the browser window slowly
3. Observe the background color changing at breakpoints
4. Use Developer Tools → Responsive Mode for accuracy

---

## Key Learning Points

* Media queries are evaluated in real time
* `min-width` and `max-width` define breakpoints
* Multiple `@media` queries can exist in the same file
* The viewport meta tag is essential for mobile responsiveness

---

## Interview & Exam Notes

* Media queries enable responsive design
* They apply conditional CSS based on device characteristics
* Commonly used with Flexbox and Grid
* Mobile-first design usually prefers `min-width`

---

## Final Summary

This file is a clean example of:

* Multiple media queries
* Well-defined breakpoints
* Visual confirmation of responsiveness

Mastering this concept is essential for modern frontend development.

---

**End of README.md**
