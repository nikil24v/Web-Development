# CSS Basics
- CSS Basics encompass the fundamental building blocks for styling web pages. This includes understanding selectors (how to target specific HTML elements), properties (the visual characteristics you want to change, like color or font size), and values (the specific settings for those properties, such as "red" or "16px"). Mastering these basics allows you to control the presentation of your website's content.

---

## CSS Ordering & Specificity

CSS ordering determines which styles apply when multiple rules target the same element.

### Priority Order (Highest to Lowest)
1. **Inline styles** - `style="color: red;"`
2. **ID selectors** - `#header`
3. **Class selectors** - `.button`
4. **Element selectors** - `p`, `div`
5. **Universal selector** - `*`

### Examples

**Specificity Wins:**
```css
/* Element selector - loses */
p { color: blue; }

/* Class selector - wins (higher specificity) */
.intro { color: green; }

/* ID selector - wins (highest specificity) */
#main { color: red; }
```

**Source Order (same specificity - last wins):**
```css
.button { background-color: blue; }
.button { background-color: red; }  /* This one wins */
```

**Inline Styles (always win):**
```html
<p style="color: yellow;">Text</p>  <!-- This wins -->
```

### The `!important` Flag
Use `!important` to override normal rules. Use sparingly.

```css
p { color: blue !important; }  /* Forces this color */
.paragraph { color: red; }     /* Won't override !important */
```

### Inheritance
Some properties inherit from parent to child: `color`, `font-family`, `font-size`

Others don't: `margin`, `padding`, `border`, `background`

```css
body { color: blue; }       /* All children inherit this */
div { margin: 10px; }       /* Children DON'T inherit this */
```

---

## CSS Rules & Syntax

### Basic Structure

A CSS rule consists of a **selector**, **properties**, and **values**:

```css
selector {
  property: value;
  property: value;
}
```

### Example

```css
p {
  color: blue;
  font-size: 16px;
  margin: 10px;
}
```

| Part | Example | Purpose |
|------|---------|---------|
| **Selector** | `p` | Targets which HTML element(s) to style |
| **Property** | `color`, `font-size` | What characteristic to change |
| **Value** | `blue`, `16px` | The specific setting for that property |

---

## Properties and Values

### What are Properties?

**Properties** are CSS keywords that specify what visual characteristic you want to change.

### What are Values?

**Values** are the specific settings you assign to properties. Each property accepts certain types of values.

### Common Properties & Values

#### **Text & Font**
```css
color: red;                           /* Text color */
font-size: 16px;                      /* Text size */
font-family: Arial, sans-serif;       /* Font type */
font-weight: bold;                    /* Text thickness (bold, 400-900) */
text-align: center;                   /* Alignment (left, center, right) */
text-decoration: underline;           /* Decoration (underline, line-through) */
```

#### **Colors & Backgrounds**
```css
background-color: lightblue;          /* Background color */
background-image: url('image.jpg');   /* Background image */
opacity: 0.5;                         /* Transparency (0-1) */
```

#### **Box Model**
```css
margin: 10px;                         /* Space outside element */
padding: 10px;                        /* Space inside element */
border: 2px solid black;              /* Border style */
width: 200px;                         /* Element width */
height: 100px;                        /* Element height */
```

#### **Layout & Display**
```css
display: block;                       /* block, inline, inline-block, flex, grid */
position: relative;                   /* relative, absolute, fixed, sticky */
flex-direction: row;                  /* flex row/column direction */
```

### Value Types

| Type | Example | Used For |
|------|---------|----------|
| **Color** | `red`, `#FF0000`, `rgb(255,0,0)` | Colors |
| **Size** | `16px`, `2em`, `50%` | Dimensions |
| **URL** | `url('image.jpg')` | Images, fonts |
| **Keyword** | `bold`, `center`, `solid` | Predefined options |
| **Number** | `0.5`, `1`, `100` | Opacity, order, z-index |

---

## CSS Comments

Comments in CSS are notes you add to your code to explain what's happening, make reminders, or document your work. Comments are **not displayed** in the browser—they're only visible in the source code.   

### Syntax

```css
/* This is a comment */
```

### Single-Line Comments

```css
/* This centers all text */
p { text-align: center; }
```

### Multi-Line Comments

```css
/*
  This is a multi-line comment.
  It can span multiple lines and is useful
  for explaining complex CSS rules. 
*/
.container {
  display: flex;
  justify-content: center;
}
```

### Use Cases

```css
/* TODO: Adjust mobile breakpoint */
@media (max-width: 768px) { ... }

/* Header section styles */
header { background-color: #333; }

/* Temporarily disabled
button { display: none; }
*/

/* Override for special pages */
.about-page h1 { color: blue; }
```

### Best Practices

- ✅ Comment complex or non-obvious CSS rules
- ✅ Use comments to explain WHY, not WHAT
- ✅ Keep comments brief and clear
- ✅ Update comments when code changes
- ❌ Don't over-comment obvious code
- ❌ Don't use comments for sensitive information

---

## CSS Selectors

A **CSS selector** is a pattern used to select HTML elements so you can apply styles to them.

### Simple Selectors

Simple selectors target elements directly by type, class, ID, or universal matching.

#### 1. **Universal Selector** (`*`)

Selects **all elements** on the page.

```css
* {
  margin: 0;
  padding: 0;
}
```

**Use:** Reset default browser styles globally.

---

#### 2. **Element (Type) Selector**

Selects all elements of a **specific HTML tag**.

```css
p {
  color: blue;
  font-size: 16px;
}

h1 {
  color: red;
}
```

**Use:** Style all paragraphs, all headings, etc. uniformly.

---

#### 3. **Class Selector** (`.`)

Selects all elements with a **specific class name**. Classes are reusable and can be applied to multiple elements.

```css
.button {
  background-color: green;
  padding: 10px;
}

.warning {
  color: orange;
}
```

**HTML:**
```html
<button class="button">Click me</button>
<p class="warning">Be careful!</p>
```

**Use:** Reusable styles for multiple elements.

---

#### 4. **ID Selector** (`#`)

Selects a **single, unique element** using its ID. IDs should not be repeated in a document.

```css
#header {
  background-color: navy;
  color: white;
}
```

**HTML:**
```html
<div id="header">Welcome</div>
```

**Use:** Style a unique, specific element once on the page.

---

### Combinators

Combinators define relationships between selectors. They combine multiple selectors to target elements based on their position in the HTML structure.

#### 1. **Descendant Combinator** (space ` `)

Selects elements that are **descendants** of a specified element (anywhere nested inside).

```css
div p {
  color: blue;
}
```

**HTML:**
```html
<div>
  <p>This is blue</p>
  <section>
    <p>This is also blue (nested deeper)</p>
  </section>
</div>

<p>This is NOT blue (not in div)</p>
```

**Use:** Style all paragraphs inside a specific container.

---

#### 2. **Child Combinator** (`>`)

Selects elements that are **direct children** of a specified element (only one level deep).

```css
div > p {
  color: green;
}
```

**HTML:**
```html
<div>
  <p>This is green (direct child)</p>
  <section>
    <p>This is NOT green (grandchild, not direct child)</p>
  </section>
</div>
```

**Use:** Target only immediate children, not nested deeper.

---

#### 3. **Adjacent Sibling Combinator** (`+`)

Selects an element that **immediately follows** another element (same parent level).

```css
h1 + p {
  font-weight: bold;
}
```

**HTML:**
```html
<h1>Title</h1>
<p>This paragraph is bold (comes right after h1)</p>
<p>This paragraph is NOT bold</p>
```

**Use:** Style the first element after a specific element.

---

#### 4. **General Sibling Combinator** (`~`)

Selects all elements that are **siblings** and come after a specified element (same parent, any position after).

```css
h1 ~ p {
  color: gray;
}
```

**HTML:**
```html
<h1>Title</h1>
<p>This is gray (sibling after h1)</p>
<div>Some content</div>
<p>This is also gray (sibling after h1)</p>
```

**Use:** Style all paragraphs that follow a heading in the same parent.

---

#### **Combinator Comparison Table**

| Combinator | Symbol | Meaning | Example |
|-----------|--------|---------|---------|
| **Descendant** | ` ` (space) | Any nested level inside | `div p` - all `<p>` in `<div>` |
| **Child** | `>` | Direct child only | `div > p` - only direct child `<p>` |
| **Adjacent Sibling** | `+` | Immediately after | `h1 + p` - first `<p>` after `<h1>` |
| **General Sibling** | `~` | All after (same parent) | `h1 ~ p` - all `<p>` after `<h1>` |

---

### Attribute Selectors

Attribute selectors target elements based on their **attributes** and attribute values.

#### 1. **Attribute Presence** (`[attribute]`)

Selects elements that **have a specific attribute**, regardless of its value.

```css
input[disabled] {
  opacity: 0.5;
}

a[target] {
  color: purple;
}
```

**HTML:**
```html
<input type="text" disabled>           <!-- Selected -->
<input type="text">                    <!-- Not selected -->
<a href="/" target="_blank">Link</a>  <!-- Selected -->
<a href="/">Link</a>                  <!-- Not selected -->
```

---

#### 2. **Exact Attribute Match** (`[attribute="value"]`)

Selects elements where the attribute **exactly matches** a specific value.

```css
input[type="password"] {
  border: 2px solid red;
}

a[target="_blank"] {
  font-weight: bold;
}
```

**HTML:**
```html
<input type="password">        <!-- Selected -->
<input type="text">            <!-- Not selected -->
<a target="_blank">Link</a>    <!-- Selected -->
<a target="_self">Link</a>     <!-- Not selected -->
```

---

#### 3. **Partial Match - Contains** (`[attribute*="value"]`)

Selects elements where the attribute **contains** a specific value anywhere.

```css
img[src*="icon"] {
  width: 32px;
}
```

**HTML:**
```html
<img src="icon-home.png">      <!-- Selected -->
<img src="logo-icon.png">      <!-- Selected -->
<img src="logo.png">           <!-- Not selected -->
```

---

#### 4. **Starts With** (`[attribute^="value"]`)

Selects elements where the attribute **starts with** a specific value.

```css
a[href^="https"] {
  color: green;
}
```

**HTML:**
```html
<a href="https://example.com">Secure Link</a>  <!-- Selected -->
<a href="http://example.com">Regular Link</a>  <!-- Not selected -->
```

---

#### 5. **Ends With** (`[attribute$="value"]`)

Selects elements where the attribute **ends with** a specific value.

```css
a[href$=".pdf"] {
  background-image: url('pdf-icon.png');
}
```

**HTML:**
```html
<a href="document.pdf">Download</a>  <!-- Selected -->
<a href="page.html">Page</a>         <!-- Not selected -->
```

---

#### 6. **Word Match** (`[attribute~="value"]`)

Selects elements where the attribute contains a **specific word** (space-separated).

```css
p[class~="highlight"] {
  background-color: yellow;
}
```

**HTML:**
```html
<p class="highlight">Selected</p>           <!-- Selected -->
<p class="text highlight important">Selected</p>  <!-- Selected -->
<p class="highlighting">Not selected</p>    <!-- Not selected -->
```

---

#### **Attribute Selector Comparison Table**

| Selector | Matches | Example |
|----------|---------|---------|
| `[attr]` | Has the attribute | `[disabled]` - any disabled element |
| `[attr="value"]` | Exact match | `[type="email"]` - email inputs only |
| `[attr*="value"]` | Contains substring | `[src*="icon"]` - src containing "icon" |
| `[attr^="value"]` | Starts with | `[href^="https"]` - URLs starting with https |
| `[attr$="value"]` | Ends with | `[href$=".pdf"]` - links to PDF files |
| `[attr~="value"]` | Contains word | `[class~="active"]` - class with "active" word |

---

### Combining Selectors

You can combine different selector types for more specific targeting:

```css
/* Class and attribute combined */
input[type="text"].required {
  border: 2px solid red;
}

/* Element, class, and descendant */
div.container p.intro {
  font-size: 18px;
}

/* Multiple attributes */
a[href^="https"][target="_blank"] {
  color: green;
}
```

---

## Opacity

**Opacity** controls the transparency of an element. It defines how see-through or solid an element appears on the page.

### What is Opacity?

Opacity is a CSS property that controls the **transparency level** of an entire element, including its background, text, borders, and all child elements.

### Syntax

```css
opacity: value;
```

### Values

- **Range:** `0` to `1` (or `0%` to `100%`)
- **`0` or `0%`** - Completely transparent (invisible)
- **`0.5` or `50%`** - Half transparent
- **`1` or `100%`** - Completely opaque (default, fully visible)

### Examples

#### Basic Opacity

```css
/* Completely transparent */
.hidden {
  opacity: 0;
}

/* Half transparent */
.semi-transparent {
  opacity: 0.5;
}

/* Fully opaque (default) */
.visible {
  opacity: 1;
}
```

**HTML:**
```html
<div class="hidden">Cannot see me</div>
<div class="semi-transparent">Partially visible</div>
<div class="visible">Fully visible</div>
```

---

#### Hover Effects

```css
.box {
  opacity: 0.7;
  transition: opacity 0.3s ease;
}

.box:hover {
  opacity: 1;
}
```

**Result:** Box becomes fully visible when you hover over it.

---

#### Image Opacity

```css
img {
  opacity: 0.8;
}

img:hover {
  opacity: 1;
}
```

---

#### Fading Effect

```css
.fade-in {
  opacity: 0;
  animation: fadeIn 2s ease-in forwards;
}

@keyframes fadeIn {
  to {
    opacity: 1;
  }
}
```

---

### Important Notes

#### 1. **Opacity vs. RGBA/HSLA Colors**

| Property | Effect | Applies To |
|----------|--------|-----------|
| **opacity** | Transparent entire element | Element + all children |
| **rgba/hsla** | Transparent only the color | Just that specific color |

**Example:**
```css
/* Opacity - makes EVERYTHING transparent */
.box {
  background-color: blue;
  opacity: 0.5;    /* Box AND text inside are both transparent */
}

/* RGBA - makes ONLY the color transparent */
.box {
  background-color: rgba(0, 0, 255, 0.5);  /* Only background is transparent */
  color: black;                             /* Text stays fully opaque */
}
```

---

#### 2. **Stacking Context**

When opacity is less than `1`, the element creates a new **stacking context**, which can affect `z-index` behavior.

```css
.background {
  opacity: 0.9;    /* Creates stacking context */
  z-index: 1;
}

.foreground {
  z-index: 2;      /* May not work as expected due to stacking context */
}
```

---

#### 3. **Performance**

Opacity is a lightweight property and doesn't affect layout or cause repaints like other properties do.

```css
/* Good for animations - uses GPU */
.element {
  opacity: 0;
  animation: fade 1s ease;
}
```

---

### Common Use Cases

```css
/* Disabled button */
button:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}

/* Watermark */
.watermark {
  opacity: 0.1;
  position: fixed;
  font-size: 48px;
}

/* Dark overlay */
.overlay {
  background-color: black;
  opacity: 0.7;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

/* Loading skeleton */
.skeleton {
  background-color: #ddd;
  opacity: 0.6;
  animation: shimmer 1s infinite;
}
```

---

### Browser Support

Opacity is supported in all modern browsers. For older browsers, use the deprecated `filter` property:

```css
.element {
  opacity: 0.5;
  filter: alpha(opacity=50);  /* IE 8 and below */
}
```

---

## CSS Units

**CSS Units** are measurements used to define sizes, spacing, distances, and other dimensional properties in CSS. Understanding when to use each unit is critical for responsive and maintainable web design.

### Absolute Units (Fixed Size)

Absolute units have a fixed size and **do not change** based on any other factors. They are useful for precise, pixel-perfect sizing.

#### **Pixels (px)**

The most common unit. Represents one pixel on the screen.

```css
.box {
  width: 200px;
  padding: 10px;
  border: 2px solid black;
}
```

**Use:** Precise sizing for buttons, borders, icons, and when you need exact dimensions.

**Pros:**
- ✅ Predictable and consistent across devices
- ✅ Easy to understand and calculate

**Cons:**
- ❌ Not responsive (fixed size doesn't adapt to screen size)

---

#### **Centimeters (cm), Millimeters (mm), Points (pt)**

Physical measurements, rarely used in modern web design.

```css
.print-layout {
  width: 21cm;     /* A4 width */
  margin: 10mm;
  font-size: 12pt; /* Print sizing */
}
```

**Use:** Print stylesheets (`@media print`) where physical dimensions matter.

---

### Relative Units (Flexible Size)

Relative units change based on their context—either the parent element's size, the font size, or the viewport. These are **preferred for responsive design**.

#### **Percentage (%)**

Relative to the **parent element's** corresponding property.

```css
.container {
  width: 800px;
}

.child {
  width: 50%;      /* 50% of 800px = 400px */
  padding: 10%;    /* 10% of parent's width */
}
```

**Use:** Responsive layouts, flexible widths and heights.

**Common use cases:**
```css
.full-width {
  width: 100%;     /* Same width as parent */
}

.half-width {
  width: 50%;      /* Half the parent width */
}

.sidebar {
  width: 25%;      /* Quarter of parent */
}
```

---

#### **em**

Relative to the **font-size** of the element itself (or the nearest parent with a font-size).

```css
html {
  font-size: 16px;
}

.container {
  font-size: 20px;   /* 20px */
  padding: 1em;      /* 1 × 20px = 20px */
  margin: 2em;       /* 2 × 20px = 40px */
}

.small {
  font-size: 0.875em;  /* 0.875 × 16px = 14px */
}
```

**Use:** Scalable padding, margins, and sizing relative to text size.

**Pros:**
- ✅ Scales proportionally with font-size
- ✅ Great for components that need to scale together

**Cons:**
- ❌ Can compound (nested em values multiply)
- ❌ Harder to calculate with nested elements

**Example of compounding:**
```css
.parent {
  font-size: 2em;      /* 32px (2 × 16px) */
}

.child {
  font-size: 1.5em;    /* 48px (1.5 × 32px) - unexpected! */
}
```

---

#### **rem (Root em)**

Relative to the **font-size of the root element** (`<html>`). Solves the compounding problem of `em`.

```css
html {
  font-size: 16px;     /* Base 1rem = 16px */
}

body {
  font-size: 1rem;     /* 16px */
  line-height: 1.5rem; /* 24px (always 1.5 × 16px) */
}

.container {
  padding: 2rem;       /* 32px (always 2 × 16px) */
}

.nested .child {
  padding: 1rem;       /* Still 16px - no compounding! */
}
```

**Use:** Global sizing, consistency across the site, responsive typography.

**Pros:**
- ✅ No compounding issues
- ✅ Easy to manage globally by changing root font-size
- ✅ Perfect for responsive design

**Best Practice:**
```css
html {
  font-size: 16px;     /* Desktop base size */
}

@media (max-width: 768px) {
  html {
    font-size: 14px;   /* Smaller base for mobile */
  }
}
```

---

#### **Viewport Width (vw) and Viewport Height (vh)**

Relative to the **size of the viewport** (browser window).

```css
/* 1vw = 1% of viewport width */
/* 1vh = 1% of viewport height */

.full-screen {
  width: 100vw;        /* Full viewport width */
  height: 100vh;       /* Full viewport height */
}

.hero {
  height: 50vh;        /* Half the viewport height */
  width: 80vw;         /* 80% of viewport width */
}
```

**Use:** Full-screen sections, responsive hero images, adaptive layouts.

**Common use case - Full-screen hero:**
```css
.hero {
  width: 100vw;
  height: 100vh;
  background-image: url('hero.jpg');
  display: flex;
  align-items: center;
  justify-content: center;
}
```

---

#### **vmin and vmax**

- **vmin:** 1% of the smaller viewport dimension (width or height)
- **vmax:** 1% of the larger viewport dimension

```css
.responsive-box {
  width: 80vmin;       /* 80% of smaller dimension */
  height: 80vmin;      /* Creates a square */
}

.large-text {
  font-size: 10vmax;   /* Large on big screens */
}
```

---

### Units Comparison Table

| Unit | Type | Example | Use Case |
|------|------|---------|----------|
| `px` | Absolute | `16px` | Precise sizing, borders, icons |
| `%` | Relative | `50%` | Responsive layouts, parent-relative sizing |
| `em` | Relative | `1.5em` | Scalable components, padding relative to font |
| `rem` | Relative | `2rem` | Global sizing, recommended for most use |
| `vw` | Relative | `100vw` | Full viewport width, responsive sections |
| `vh` | Relative | `50vh` | Full viewport height, hero sections |
| `vmin` | Relative | `80vmin` | Responsive sizing based on smaller dimension |
| `vmax` | Relative | `10vmax` | Responsive sizing based on larger dimension |

---

### Unit Selection Guide

```css
/* Text and font sizes - use rem for consistency */
.heading {
  font-size: 2rem;
}

/* Padding/Margin - use rem or em */
.container {
  padding: 1.5rem;
  margin: 1rem;
}

/* Widths in layouts - use % for flexibility */
.sidebar {
  width: 25%;
}

.main-content {
  width: 75%;
}

/* Full-screen sections - use vh/vw */
.hero {
  height: 100vh;
  width: 100vw;
}

/* Precise measurements - use px */
button {
  border: 1px solid black;
  padding: 8px 12px;
}

/* Responsive text - use vw or vmin */
.responsive-title {
  font-size: 5vw;      /* Scales with viewport */
}
```

---

### Best Practices

1. **Use `rem` for consistent global sizing** - Makes it easy to scale the entire site
2. **Use `%` for layout widths** - Responsive and parent-aware
3. **Use `em` for component-specific scaling** - When padding/margins should scale with text
4. **Use `px` for borders and small details** - When precision matters
5. **Use `vw`/`vh` for full-screen elements** - Hero sections, modals, overlays
6. **Avoid mixing too many units** - Stick to 2-3 units per project for consistency
```

---

## Display Properties

The **display** property is one of the most important CSS properties. It controls how an element is laid out and how it interacts with other elements on the page. Every HTML element has a default display value, but you can change it using the display property.

### Default Display Values

By default, HTML elements have one of two display values:

- **Block elements** - `<div>`, `<p>`, `<h1>-<h6>`, `<ul>`, `<ol>`, `<li>`, `<section>`, `<header>`, etc.
- **Inline elements** - `<span>`, `<a>`, `<strong>`, `<em>`, `<img>`, `<button>`, etc.

---

### Display Values

#### **1. `display: block`**

Block elements start on a **new line** and take up the **full available width** (stretch from left to right).

**Characteristics:**
- Starts on a new line
- Takes 100% of available width (stretches horizontally)
- Height and width properties work
- Margin and padding are fully respected (top, bottom, left, right)
- Stacks vertically by default

**Example:**
```css
.box {
  display: block;
  width: 200px;
  height: 100px;
  background-color: blue;
  margin: 10px;
  padding: 20px;
}
```

**HTML:**
```html
<div class="box">Box 1</div>
<div class="box">Box 2</div>
<div class="box">Box 3</div>
```

**Result:** All three boxes appear in separate lines, each taking full width.

**Common block elements:**
```css
div, p, h1-h6, ul, ol, li, section, article, header, footer, nav {
  display: block;  /* Default */
}
```

---

#### **2. `display: inline`**

Inline elements **flow within text** and only take up as much width as necessary. They sit side by side on the same line.

**Characteristics:**
- Sits on the same line as other inline elements
- Only takes up as much width as needed
- Width and height properties **do NOT work**
- Horizontal margin and padding work, vertical margin and padding **do NOT work** (no space above/below)
- Cannot create space above/below using margin or padding

**Example:**
```css
.inline-text {
  display: inline;
  background-color: yellow;
  margin: 10px;           /* Only left/right work */
  padding: 5px 10px;      /* Only left/right work fully */
}
```

**HTML:**
```html
<span class="inline-text">Text 1</span>
<span class="inline-text">Text 2</span>
<span class="inline-text">Text 3</span>
```

**Result:** All three elements appear on the same line, flowing like text.

**Common inline elements:**
```css
span, a, strong, em, img, button, label {
  display: inline;  /* Default */
}
```

---

#### **3. `display: inline-block`**

A hybrid between `block` and `inline`. Elements sit on the same line **but respect width, height, and all margin/padding values**.

**Characteristics:**
- Sits on the same line as other inline/inline-block elements
- Width and height properties **DO work**
- All margin and padding properties work (top, bottom, left, right)
- Can be positioned precisely
- Treats elements as both inline and block

**Example:**
```css
.button {
  display: inline-block;
  width: 150px;
  height: 40px;
  background-color: green;
  color: white;
  padding: 10px;
  margin: 5px;
  text-align: center;
}
```

**HTML:**
```html
<button class="button">Button 1</button>
<button class="button">Button 2</button>
<button class="button">Button 3</button>
```

**Result:** All three buttons appear on the same line with proper spacing.

**Comparison Table:**
| Property | Block | Inline | Inline-Block |
|----------|-------|--------|--------------|
| New line | ✅ Yes | ❌ No | ❌ No |
| Full width | ✅ Yes | ❌ No | ❌ No |
| Width works | ✅ Yes | ❌ No | ✅ Yes |
| Height works | ✅ Yes | ❌ No | ✅ Yes |
| Vertical margin | ✅ Yes | ❌ No | ✅ Yes |
| Horizontal margin | ✅ Yes | ✅ Yes | ✅ Yes |

---

#### **4. `display: none`**

Completely **removes the element** from the document flow. The element takes up no space at all.

**Characteristics:**
- Element is hidden and takes up no space
- Not part of the document layout
- Useful for hiding/showing elements with JavaScript
- Different from `visibility: hidden` (which hides but keeps the space)

**Example:**
```css
.hidden {
  display: none;
}

/* Show on hover */
.menu-item:hover .submenu {
  display: block;
}
```

**HTML:**
```html
<div class="hidden">This is not visible and takes no space</div>
<div>This is visible</div>
```

**Comparison: `display: none` vs `visibility: hidden`**

```css
/* Display: none - removes from layout */
.element1 {
  display: none;      /* Takes no space */
}

/* Visibility: hidden - keeps space but hides */
.element2 {
  visibility: hidden; /* Still takes up space */
  opacity: 0;         /* Alternative: transparent but clickable */
}
```

---

#### **5. `display: flex`**

Creates a **flexible container** for one-dimensional layouts. All children become flex items and align flexibly.

**Characteristics:**
- Makes children sit on the same row (by default)
- Distributes space evenly among children
- Aligns items flexibly using `justify-content`, `align-items`, etc.
- Powerful for navigation, buttons, cards, and responsive layouts
- Can reverse direction, wrap, and more

**Basic Example:**
```css
.flex-container {
  display: flex;
  background-color: lightgray;
  padding: 10px;
  gap: 10px;              /* Space between items */
}

.flex-container div {
  background-color: blue;
  color: white;
  padding: 20px;
  flex: 1;                /* Each item takes equal space */
}
```

**HTML:**
```html
<div class="flex-container">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>
```

**Result:** Three equal-width boxes in a row with space between them.

**Common Flexbox Properties:**
```css
.container {
  display: flex;
  
  /* Direction */
  flex-direction: row;              /* row, column, row-reverse, column-reverse */
  
  /* Wrap to new line */
  flex-wrap: wrap;                  /* wrap, nowrap, wrap-reverse */
  
  /* Main axis alignment (horizontal by default) */
  justify-content: center;          /* flex-start, center, flex-end, space-between, space-around, space-evenly */
  
  /* Cross axis alignment (vertical by default) */
  align-items: center;              /* flex-start, center, flex-end, stretch */
  
  /* Space between items */
  gap: 15px;                        /* Uniform gap between flex items */
}

.item {
  flex: 1;                          /* Grow equally */
  flex-grow: 1;                     /* How much to grow */
  flex-shrink: 1;                   /* How much to shrink */
  flex-basis: 100px;                /* Base size before growing/shrinking */
}
```

---

#### **6. `display: grid`**

Creates a **two-dimensional grid layout** with rows and columns. Perfect for complex, structured layouts.

**Characteristics:**
- Defines both rows AND columns
- Precise control over placement
- Can overlap items
- Great for page layouts, dashboards, photo galleries
- More complex than flexbox but more powerful for 2D layouts

**Basic Example:**
```css
.grid-container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;  /* 3 equal columns */
  grid-template-rows: 100px 100px;     /* 2 rows of 100px */
  gap: 10px;                           /* Space between grid items */
  background-color: lightgray;
}

.grid-item {
  background-color: blue;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
}
```

**HTML:**
```html
<div class="grid-container">
  <div class="grid-item">1</div>
  <div class="grid-item">2</div>
  <div class="grid-item">3</div>
  <div class="grid-item">4</div>
  <div class="grid-item">5</div>
  <div class="grid-item">6</div>
</div>
```

**Result:** 3x2 grid layout with equal spacing.

**Grid Properties:**
```css
.container {
  display: grid;
  
  /* Define columns */
  grid-template-columns: 200px 1fr 150px;  /* Fixed, flexible, fixed */
  grid-template-columns: repeat(3, 1fr);   /* 3 equal columns */
  
  /* Define rows */
  grid-template-rows: 100px auto 100px;
  
  /* Gap between items */
  gap: 15px;
  column-gap: 10px;
  row-gap: 20px;
}

.item {
  grid-column: 1 / 3;     /* Span columns 1 to 3 */
  grid-row: 1 / 2;        /* Span row 1 to 2 */
}
```

---

### Display Values Comparison

| Value | Behavior | Use Case |
|-------|----------|----------|
| `block` | Full width, new line | Paragraphs, sections, containers |
| `inline` | Flow with text, no sizing | Links, bold/italic text |
| `inline-block` | Side-by-side with sizing | Buttons, inline images |
| `none` | Hidden, no space | Hide/show with JS |
| `flex` | Flexible 1D layout | Navigation, buttons, cards |
| `grid` | Precise 2D layout | Page layouts, galleries |

---

### Practical Examples

#### Navigation Bar with Flexbox
```css
nav {
  display: flex;
  justify-content: space-around;
  background-color: navy;
  padding: 10px;
}

nav a {
  color: white;
  text-decoration: none;
  padding: 10px 15px;
}
```

#### Product Card Grid
```css
.product-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
  padding: 20px;
}

.product-card {
  background-color: white;
  border: 1px solid #ddd;
  border-radius: 5px;
  padding: 15px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}
```

#### Sidebar Layout
```css
.page {
  display: flex;
}

.sidebar {
  width: 200px;
  background-color: #f0f0f0;
  padding: 20px;
}

.main-content {
  flex: 1;
  padding: 20px;
}
```

---

### Browser Support

All display values mentioned above have excellent browser support in modern browsers (Chrome, Firefox, Safari, Edge). Grid and Flexbox are fully supported in all modern browsers.

For older browser support, use prefixes:
```css
.container {
  display: -webkit-flex;     /* Safari, older Chrome */
  display: flex;             /* Modern browsers */
}

