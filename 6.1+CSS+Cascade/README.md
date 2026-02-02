Cascading = falling in layers

CSS applies styles in layers of priority. When multiple rules target the same element, the browser doesn’t panic — it cascades through rules and picks the winner using a fixed system.

Correct Priority Order (Top → Bottom)

🥇 !important — Highest
This beats everything, even inline styles.

Example:
p {
  color: blue !important;
}

# <p style="color: red;">Hello</p>

Result: Blue wins.

🥈 Inline CSS
Styles inside the tag itself:
<p style="color: red;">Hello</p>
This beats internal and external CSS.


🥉 Internal CSS
Inside <style> in the HTML file.

4️⃣ External CSS
From .css files.

# CSS Specificity & Inheritance — Complete Guide

This document explains how CSS decides which style rule is applied and how styles are passed from parent elements to child elements.

---

## 1. CSS Specificity

### What is Specificity?

**Specificity** is the scoring system CSS uses to determine which rule is more powerful when multiple rules target the same element.

> The rule with the **higher specificity score wins.**

---

## How Specificity is Calculated

CSS assigns values to different types of selectors. The score is written as a **4-part format**:

```text
(A, B, C, D)

| Letter | Selector Type                  | Examples                          |
| ------ | ------------------------------ | --------------------------------- |
| A      | Inline styles                  | `style="color:red"`               |
| B      | ID selectors                   | `#header`, `#main`                |
| C      | Class, attribute, pseudo-class | `.box`, `[type="text"]`, `:hover` |
| D      | Element, pseudo-element        | `p`, `div`, `::before`            |


Specificity Priority Order (Low → High)
(D) Element
(C) Class / Attribute / Pseudo-class
(B) ID
(A) Inline

What is Inheritance?
Inheritance is the process where some CSS properties automatically pass from a parent element to its children.

| Property      | Example           |
| ------------- | ----------------- |
| `color`       | Text color        |
| `font-family` | Font type         |
| `font-size`   | Text size         |
| `visibility`  | Visibility state  |
| `cursor`      | Mouse cursor type |
| `line-height` | Line spacing      |


| Property     | Example                |
| ------------ | ---------------------- |
| `margin`     | Space outside element  |
| `padding`    | Space inside element   |
| `border`     | Element border         |
| `background` | Background color/image |
| `width`      | Element width          |
| `height`     | Element height         |

