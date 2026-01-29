Difference Between px, pt, em, and rem

    1. px — Pixels (Absolute Unit)
    What it is
    A pixel is a fixed unit of measurement on the screen.

    How it works
    1px = one screen pixel (logical pixel)
    Size stays the same regardless of parent or root font size

    Why it’s used
    Precise control
    Perfect for borders, icons, and exact layouts

    p {
        font-size: 16px;
    }

    px = fixed size

    2. pt — Points (Print Unit)

    What it is
    A point is a unit used mainly in printing, not screens.

    How it works
    1pt = 1/72 of an inch
    Browser converts it to pixels internally

    Why it’s used
    Print styles (PDFs, documents)
    Rarely used in modern web design

    p {
         font-size: 12pt;
    }

    pt = paper

    3. em — Relative to Parent
    
    What it is
    A relative unit based on the font size of the parent element.

    How it works
    1em = parent’s font size
    If parent is 16px → 1em = 16px
    If parent is 20px → 1em = 20px

    Why it’s used
    Makes layouts flexible and scalable
    Good for components that scale together

    div {
        font-size: 20px;
    }

    p {
    font-size: 1.5em; /* 30px */
    }

    em = parent

    4. rem — Relative to Root

    What it is
    A relative unit based on the font size of the root element (html).

    How it works
    1rem = html font size
    Default: 1rem = 16px (unless changed)

    Why it’s used
    Predictable scaling
    Best for responsive design
    Avoids nesting problems of em

    html {
    font-size: 16px;
    }

    p {
    font-size: 2rem; /* 32px */
    }

    rem = root


## Files
- **`index.html`** – Webpage structure and internal CSS
- **External Resource** – Google Font (Caveat)


## HTML Structure

### `<!DOCTYPE html>`
Declares the document as **HTML5**.

### `<html lang="en">`
Root element of the page. The `lang` attribute helps accessibility tools and browsers understand the page language.

### `<head>`
Contains:
- `<meta charset="UTF-8">` – Enables full character support
- `<title>` – Sets the browser tab name
- `<style>` – Internal CSS rules
- `<link>` – Links the Google Font stylesheet

### `<body>`
Visible content:
- `<h1>` – Page heading
- `<p>` elements – Each demonstrates a different CSS property using a class

---

## CSS Used

```css
body {
  background-color: cornflowerblue;
  color: white;
  font-size: 18px;
}

.cl {
  color: coral;
}

.ft {
  font-size: 2rem;
}

.fw {
  font-weight: 900;
}

.ff {
  font-family: 'Caveat', cursive;
  font-weight: 400;
}

.ta {
  text-align: right;
}

html {
  font-size: 30px;
}
```

---

## Properties Used – What, Type, and Why

---

### 1. `background-color`
**Type:** Visual / Background Property  
**What:** Sets the background color of an element  
**Why:** Improves contrast and visual appeal  
**Used On:** `body` to color the full page background

---

### 2. `color`
**Type:** Text Property  
**What:** Sets the text color  
**Why:** Improves readability and highlights content  
**Used On:** `.cl` to change text to coral

---

### 3. `font-size`
**Type:** Typography Property  
**What:** Controls the size of text  
**Why:** Creates visual hierarchy and emphasis  
**Used On:**  
- `body` → Base size (18px)  
- `.ft` → Uses `2rem` for scalable sizing

---

### 4. `font-weight`
**Type:** Typography Property  
**What:** Controls text thickness (boldness)  
**Why:** Highlights important text  
**Used On:** `.fw` (900 = very bold), `.ff` (400 = normal)

---

### 5. `font-family`
**Type:** Typography Property  
**What:** Changes the font style of text  
**Why:** Improves design and readability  
**Used On:** `.ff` to apply the Google Font "Caveat"

---

### 6. `text-align`
**Type:** Layout / Text Property  
**What:** Aligns text horizontally  
**Why:** Controls layout and presentation  
**Used On:** `.ta` to align text to the right

---

## Root Font Size and `rem`

### What `rem` Means
`rem` is relative to the **root (`html`) font size**.

```css
html {
  font-size: 30px;
}
```

```css
.ft {
  font-size: 2rem;
}
```

### Result
- `1rem = 30px`  
- `2rem = 60px`

### Why This is Used
- Makes text **responsive and scalable**
- One change in `html` updates the whole site

---

## Google Font Linking

### Correct Link
```html
<link href="https://fonts.googleapis.com/css2?family=Caveat:wght@400&display=swap" rel="stylesheet">
```

### Why It’s Used
- Loads a custom font from Google
- Improves typography and design quality
- Allows consistent fonts across devices

---

## Why Classes Are Used

Each `<p>` element uses a **class selector** because:
- Classes are **reusable**
- They represent **styling categories**, not unique elements
- They keep CSS clean and scalable

---

## Specificity Rule

**ID > Class > Element**

Classes are used here for clean styling without unnecessary priority.

---

## Learning Summary

- `color` changes text color
- `background-color` styles page background
- `font-size` controls text size
- `rem` scales text from the root element
- `font-weight` controls boldness
- `font-family` changes typography
- `text-align` controls layout
- Google Fonts allow custom web fonts
- Classes are best for reusable styles

---

## Reference
MDN Web Docs – CSS  
https://developer.mozilla.org/en-US/docs/Web/CSS  
Google Fonts  
https://fonts.google.com
