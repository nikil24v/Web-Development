# HTML + CSS Colors – README

This project demonstrates how to style a webpage using **internal CSS** and **external CSS**. It focuses on using **color and background properties** to control how text and the page look.

---

## Files
- **`index.html`** – Contains the webpage structure and internal CSS
- **`style.css`** – Optional external stylesheet linked to the HTML file

---

## What This Page Does

The webpage displays:
- A full-page background color
- A main heading (`<h1>`) with custom text and background color
- A subheading (`<h2>`) with custom text and background color

This shows how CSS properties change both **text appearance** and **element backgrounds**.

---

## HTML Structure

### `<!DOCTYPE html>`
Tells the browser this is an **HTML5 document**.

### `<html lang="en">`
Root element of the page. The `lang` attribute helps browsers and screen readers understand the page language.

### `<head>`
Contains metadata and styles:
- `<meta charset="UTF-8">` – Supports all characters
- `<title>` – Sets the browser tab name
- `<style>` – Internal CSS
- `<link>` – Connects external CSS

### `<body>`
Visible content:
- `<h1>` – Main heading
- `<h2>` – Subheading

---

## CSS Used (Internal Styling)

```css
html {
  background-color: antiquewhite;
}

h1 {
  color: whitesmoke;
  background-color: darkseagreen;
}

h2 {
  color: #FAF8F1;
  background-color: #C58940;
}
```

---

## CSS Properties Used – What, Type, and Why

---

### 1. `background-color`

**Property Type:**  
Visual / Background Property

**What it does:**  
Sets the background color of an element.

**Why it is used:**  
- Improves readability  
- Separates sections visually  
- Makes the page more attractive

**Where it is used:**  
- On `html` → colors the full webpage background  
- On `h1` and `h2` → highlights headings

**Example:**
```css
background-color: antiquewhite;
```

---

### 2. `color`

**Property Type:**  
Text / Font Property

**What it does:**  
Sets the color of the text inside an element.

**Why it is used:**  
- Improves contrast with the background  
- Makes text easier to read  
- Helps important content stand out

**Where it is used:**  
- On `h1` → changes heading text color  
- On `h2` → changes subheading text color

**Example:**
```css
color: whitesmoke;
```

---

## Color Value Types Used

### Named Colors
Example:
```css
color: whitesmoke;
background-color: darkseagreen;
```
**Why used:**  
Easy to read and remember for basic styling.

### HEX Colors
Example:
```css
color: #FAF8F1;
background-color: #C58940;
```
**Why used:**  
Gives precise control over color shades, commonly used in professional designs.

---

## Internal vs External CSS

### Internal CSS
Written inside the `<style>` tag in the HTML file.

**Why used:**  
- Quick testing  
- Styling a single page  
- Learning and experimenting

---

### External CSS
Written in a `.css` file and linked using:
```html
<link rel="stylesheet" href="style.css">
```

**Why used:**  
- Clean and organized code  
- Reusable styles for multiple pages  
- Easier maintenance

---

## Learning Summary

- `color` controls **text appearance**
- `background-color` controls **element background**
- Named colors are **simple and readable**
- HEX colors are **precise and professional**
- Internal CSS is good for **quick styling**
- External CSS is best for **real projects**
- The `html` selector styles the **entire page**
- `h1` and `h2` selectors style **headings**

---

## Reference
MDN Web Docs – CSS  
https://developer.mozilla.org/en-US/docs/Web/CSS
