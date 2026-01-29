# CSS Box Model – README

This project demonstrates how the **CSS Box Model** works using three `<div>` elements. It shows how **content, padding, border, and margin** affect the size, spacing, and layout of elements on a webpage.

---

## Files
- **`index.html`** – Contains the webpage structure and internal CSS

---

## What This Page Does

The webpage displays **three colored boxes** aligned using margins.  
Each box demonstrates a different combination of:
- **Padding**
- **Border**
- **Margin**
- **Background color**

This helps visualize how spacing and sizing work in CSS.

---

## What is the CSS Box Model?

Every HTML element is treated as a box made of four layers:

1. **Content** – The actual text or elements inside  
2. **Padding** – Space between content and border  
3. **Border** – Line around the padding and content  
4. **Margin** – Space outside the border, between elements  

**Memory Tip:**  
**Content → Padding → Border → Margin (Inside to Outside)**

---

## Base Styling (All Boxes)

```css
div {
  height: 200px;
  width: 200px;
}
```

**What:** Sets the size of all boxes  
**Why:** Keeps every box uniform so spacing effects are easy to see

---

## Box 1 – Padding + Border

```css
#first {
  background-color: aquamarine;
  padding: 20px;
  border: 10px solid black;
}
```

**What it shows:**
- **Padding** increases space inside the box
- **Border** draws a visible outline

**Why used:**  
To demonstrate how padding increases the space between content and the border.

---

## Box 2 – Uneven Borders + Margin

```css
#second {
  background-color: blueviolet;
  border: solid black;
  border-width: 20px 10px;
  margin-left: 260px;
}
```

**What it shows:**
- Different border sizes for top/bottom and left/right
- Horizontal movement using margin

**Why used:**  
To demonstrate how borders and margins affect positioning.

---

## Box 3 – Border + Margin

```css
#third {
  background-color: brown;
  border: 10px solid black;
  margin-left: 40px;
}
```

**What it shows:**
- Standard border
- Fine positioning using smaller margin

**Why used:**  
To demonstrate spacing between elements using margins.

---

## Paragraph Styling Note

The paragraph inside the first box should have its default margin removed:

```css
p {
  margin: 0;
}
```

**Why:**  
Browsers add default margins to `<p>` tags. Removing them ensures the padding effect is clearly visible.

---

## Layout Concept

Margins are adjusted so the **corners of each box visually touch**, creating a stepped layout. This demonstrates how horizontal spacing is controlled using `margin-left`.

---

## Learning Summary

- Understand the **4 layers of the Box Model**
- Control size using `width` and `height`
- Create space inside elements using `padding`
- Outline elements using `border`
- Control spacing between elements using `margin`
- Learn how different border widths affect layout

---

## Reference
MDN Web Docs – CSS Box Model  
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model
