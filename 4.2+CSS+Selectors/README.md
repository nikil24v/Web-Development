# CSS Selectors – Complete README

This project demonstrates how **CSS selectors** are used to target and style different parts of an HTML document. It explains each selector type with clear examples and shows how they work in a real webpage. The goal is to understand how CSS connects to HTML, how selector priority works, and how to write clean, readable, and maintainable CSS.

---

## Project Overview

This webpage displays notes about CSS selectors and styles them using an external CSS file. Each element on the page is styled using a different selector to visually demonstrate how CSS targets HTML elements in real-world scenarios.

---

## Files Included

- **`index.html`**  
  Contains the structure and content of the webpage.

- **`solution-style.css`**  
  Contains all the CSS rules that apply styles using different selectors.

---

## HTML Structure

### `<html>` Tag  
The `<html>` tag is the root element of the webpage. It wraps all content and tells the browser that this is an HTML document.

### `<head>` Section  
Includes:
- `<meta charset="UTF-8">` – Defines character encoding  
- `<title>` – Sets the browser tab title  
- `<link rel="stylesheet">` – Connects the external CSS file  

### `<body>` Section  
Contains:
- Headings (`<h1>`, `<h2>`)  
- A paragraph (`<p>`)  
- An ordered list (`<ol>`) with list items (`<li>`)  

Each list item demonstrates a different type of CSS selector.

---

## What is a CSS Selector?

A **CSS selector** is a pattern used to select one or more HTML elements so styles can be applied to them.

### Basic Syntax

```css
selector {
  property: value;
}

Types of CSS Selectors

    1. Universal Selector

    Syntax:
    * {
    text-align: center;
    }


    Explanation:
    Selects all elements on the page. It is commonly used for global styling such as setting default fonts, alignment, or resetting margins and padding.

    2. Element (Type) Selector

    Syntax:
    p {
    color: red;
    }

    Explanation:
    Targets all elements of a specific HTML tag.

    3. Class Selector

    Syntax:
    .note {
    font-size: 20px;
    }

    Explanation:
    Targets all elements that share the same class name. Classes are reusable and can be applied to multiple elements.

    4.ID Selector

    Syntax:
    #id-selector-demo {
    color: green;
    }

    Explanation:
    Targets a single, unique element using its ID. IDs should not be repeated in a document.

    5. Attribute Selector

    Syntax:
    li[value="4"] {
    color: blue;
    }

    Explanation:
    Targets elements based on the presence or value of an attribute.

    6. Group Selector

    Syntax:
    h1, h2, p {
    color: black;
    }

    Explanation:
    Targets multiple elements at once and applies the same style to all of them.

# Reference
MDN Web Docs – CSS Selectors
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors