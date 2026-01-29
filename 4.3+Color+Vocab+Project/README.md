# CSS Selectors – Quick Revision README

This project explains how **CSS selectors** are used to connect HTML elements with visual styles. It focuses on *what each selector is*, *why it is used*, and *when to use it* so the concepts are easy to remember during revision.

---

## Files
- **`index.html`** – Defines the structure and content of the webpage  
- **`style.css`** – Defines how the content looks using CSS selectors  

---

## What is CSS?

**CSS (Cascading Style Sheets)** is used to control the appearance of a webpage.  
HTML creates the structure, and CSS makes it look clean, readable, and professional.

**Why CSS is used:**  
- Separates design from content  
- Makes websites easier to maintain  
- Allows consistent styling across multiple pages  

---

## CSS Code Used

```css
img {
  height: 200px;
  width: 200px;
}

.color-title {
  font-weight: normal;
}

#red { color: red; }
#blue { color: blue; }
#orange { color: orange; }
#green { color: green; }
#yellow { color: yellow; }
```

---

## Selector Types – What, Why, and When

---

### 1. Element Selector (`img`)

**What it is:**  
Targets all elements of a specific HTML tag.

**Why it is used:**  
To apply a common style to every element of the same type without repeating code.

**When to use it:**  
When all elements of one tag should look the same.

```css
img {
  width: 200px;
  height: 200px;
}
```

**Memory Tip:**  
*Element selector = control all of one kind*

---

### 2. Class Selector (`.color-title`)

**What it is:**  
Targets elements that share the same class name.

**Why it is used:**  
To apply the same style to many elements while keeping flexibility.

**When to use it:**  
When multiple elements need the same style, but not the whole tag type.

```css
.color-title {
  font-weight: normal;
}
```

**Memory Tip:**  
*Class = reusable style*

---

### 3. ID Selector (`#red`, `#blue`, etc.)

**What it is:**  
Targets one unique element using its ID.

**Why it is used:**  
To style or control a specific element without affecting others.

**When to use it:**  
When only one element needs a special style or behavior.

```css
#red {
  color: red;
}
```

**Memory Tip:**  
*ID = one and only one*

---

## Example HTML Usage

```html
<h1 class="color-title">Color List</h1>

<h2 id="red">Red</h2>
<h2 id="blue">Blue</h2>
<h2 id="orange">Orange</h2>
<h2 id="green">Green</h2>
<h2 id="yellow">Yellow</h2>

<img src="image.png" alt="Sample Image">
```

---

## Linking CSS to HTML

**What it is:**  
Connects the external CSS file to the HTML file.

**Why it is used:**  
So the browser knows where to get the styling rules.

**How to use it:**  
Place inside the `<head>` section.

```html
<link rel="stylesheet" href="style.css">
```

---

## Selector Priority (Specificity)

**Why it matters:**  
If multiple styles apply to the same element, the browser chooses the one with higher priority.

**Order:**  
1. ID Selector (highest)  
2. Class Selector (medium)  
3. Element Selector (lowest)

**Memory Tip:**  
*ID beats Class, Class beats Tag*

---

## Learning Summary

- **HTML builds the structure**  
- **CSS controls the appearance**  
- **Element selectors** style all of one type  
- **Class selectors** reuse styles  
- **ID selectors** target one unique element  
- **Specificity decides which style wins**

---

## Reference
MDN Web Docs – CSS Selectors  
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors
