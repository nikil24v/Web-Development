# CSS Position, Offsets, Z-Index & Border-Radius — Complete Guide

This document explains how CSS controls **where elements are placed**, **how they move**, **which element appears on top**, and **how to create rounded shapes and circles**.

---

## 1. What is CSS `position`?

The `position` property defines **how an element is placed in the document** and how `top`, `right`, `bottom`, and `left` affect it.

By default, elements follow the **normal document flow** (top to bottom).

---

## 2. Position Types

| Value | Meaning | Keeps Space? | Moves With Scroll? | Reference Point |
|-------|---------|--------------|---------------------|------------------|
| `static` | Default flow | Yes | Yes | Normal flow |
| `relative` | Moves from itself | Yes | Yes | Its original position |
| `absolute` | Floats inside parent | No | Yes | Nearest positioned parent |
| `fixed` | Sticks to screen | No | No | Browser window |
| `sticky` | Scroll then stick | Yes → No | No (after stick) | Scroll container |

---

## 3. Offset Properties (`top`, `right`, `bottom`, `left`)

### What They Are  
These are **offset properties**, not borders.  
They **move an element** away from a reference edge.

### Rule  
They only work when `position` is:
```css
relative | absolute | fixed | sticky

They do NOT work with:
static

| Property | Meaning                   |
| -------- | ------------------------- |
| `top`    | Distance from top edge    |
| `bottom` | Distance from bottom edge |
| `left`   | Distance from left edge   |
| `right`  | Distance from right edge  |

5. Reference Point (Most Important Rule)
What the offsets are measured from depends on position:
| Position   | Offsets Measured From     |
| ---------- | ------------------------- |
| `relative` | Its original position     |
| `absolute` | Nearest positioned parent |
| `fixed`    | Browser window (viewport) |
| `sticky`   | Scroll container          |

Basic Syntax
element {
  position: relative | absolute | fixed | sticky;
  top: value;
  left: value;
}

Z-Index (Layer Control)

What It Does
Controls which element appears on top when elements overlap.

Rules
Only works on positioned elements

Higher number = closer to the user

Syntax:
.box1 {
  position: absolute;
  z-index: 1;
}

.box2 {
  position: absolute;
  z-index: 2;
}

Result:
.box2 appears above .box1.

border-radius

What It Does
Rounds the corners of an element.

Common Values
| Value  | Effect                     |
| ------ | -------------------------- |
| `0`    | Sharp corners              |
| `10px` | Slightly rounded           |
| `50%`  | Circle (if width = height) |
