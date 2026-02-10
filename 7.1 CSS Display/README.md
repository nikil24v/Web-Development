# CSS Display Properties

This document explains the **four core CSS display values** that beginners and exams/interviews usually focus on:

* `display: block`
* `display: inline`
* `display: inline-block`
* `display: none`

No flex, no grid — only the fundamentals.

---

## 1. display: block

### Definition

A **block-level element** starts on a new line and takes up the full available width by default.

### Key Characteristics

* Starts on a **new line**
* Takes **full width** of the parent (unless width is set)
* Behaves like a **rectangular box**

### Properties Support

* Width: ✅ Works
* Height: ✅ Works
* Margin: ✅ Works (all sides)
* Padding: ✅ Works (all sides)

### Common Block Elements

```
<div>
<p>
<h1> to <h6>
<section>
<article>
```

### Example

```css
.box {
  display: block;
  width: 200px;
  height: 100px;
  background-color: steelblue;
}
```

### Mental Model

> Block means: **"I take the entire row."**

---

## 2. display: inline

### Definition

An **inline element** flows within text and does not start on a new line.

### Key Characteristics

* Does **not** start a new line
* Takes **only content width**
* Flows like text

### Properties Support

* Width: ❌ Does NOT work
* Height: ❌ Does NOT work
* Margin-top / Margin-bottom: ❌ Ignored
* Margin-left / Margin-right: ✅ Works
* Padding: ⚠️ Works visually but does not affect vertical layout

### Common Inline Elements

```
<span>
<a>
<strong>
<em>
```

### Example

```css
.text {
  display: inline;
  background-color: orange;
  width: 200px; /* ignored */
}
```

### Mental Model

> Inline means: **"I behave like a word in a sentence."**

---

## 3. display: inline-block

### Definition

An **inline-block element** stays inline with others but behaves like a block internally.

### Why It Is Important

This is the most practical display value for UI elements.

### Key Characteristics

* Does **not** start a new line
* Allows full box control

### Properties Support

* Width: ✅ Works
* Height: ✅ Works
* Margin: ✅ Works
* Padding: ✅ Works

### Example

```css
.card {
  display: inline-block;
  width: 150px;
  height: 100px;
  margin: 10px;
  background-color: green;
}
```

### Common Use Cases

* Buttons
* Navigation items
* Small cards
* Badges

### Mental Model

> Inline-block means: **"I stay in line, but I am still a box."**

---

## 4. display: none

### Definition

The element is **completely removed from the layout** and does not exist visually or spatially.

### Key Characteristics

* Element is **not visible**
* Takes **zero space**
* Other elements behave as if it never existed

### Example

```css
.popup {
  display: none;
}
```

### Important Notes

* No width or height
* No margin or padding
* No click or hover events

### display: none vs visibility: hidden

| Property       | display: none | visibility: hidden |
| -------------- | ------------- | ------------------ |
| Visible        | ❌            | ❌                 |
| Space occupied | ❌            | ✅                 |
| Affects layout | ❌            | ✅                 |

### Mental Model

> display: none means: **"I do not exist."**

---

## Final Comparison Table

| Display Value | New Line | Width/Height | Takes Space |
| ------------- | -------- | ------------ | ----------- |
| block         | ✅        | ✅            | ✅           |
| inline        | ❌        | ❌            | ✅           |
| inline-block  | ❌        | ✅            | ✅           |
| none          | ❌        | ❌            | ❌           |

---

## Interview Rule (Very Important)

> If width and height don’t work → it is `inline`.
>
> If it jumps to a new line → it is `block`.
>
> If it stays inline and still obeys box rules → it is `inline-block`.
>
> If it disappears completely → it is `none`.

---

**End of File**
