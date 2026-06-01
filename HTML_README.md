# HTML Basics

## What is Markup Language?

Markup languages are systems for annotating text to make it readable by both humans and computers. They use tags to define elements within a document, specifying how the text should be structured, formatted, and displayed.

**Example:** HTML uses `<p>` for paragraphs and `<h1>` for headings to structure web content.

---

## Introduction to HTML

**HTML (HyperText Markup Language)** is the foundational language of the Web. It defines the meaning and structure of web content.

### Key Concepts

- **Hypertext:** Links that connect web pages to one another. Links are fundamental to the Web.
- **Markup:** Special tags annotate text, images, and other content for display in browsers.
- **Structure:** HTML focuses on content organization, while CSS handles appearance and JavaScript handles behavior.

### Common HTML Elements

```html
<head>      <!-- Metadata about the page -->
<title>     <!-- Page title in browser tab -->
<body>      <!-- Main content -->
<header>    <!-- Header section -->
<footer>    <!-- Footer section -->
<nav>       <!-- Navigation -->
<main>      <!-- Main content area -->
<article>   <!-- Article content -->
<section>   <!-- Content section -->
<p>         <!-- Paragraph -->
<h1>-<h6>  <!-- Headings -->
<img>       <!-- Image -->
<a>         <!-- Link -->
<ul>, <ol>, <li>  <!-- Lists -->
<div>, <span>     <!-- Generic containers -->
```

📚 **Reference:** [MDN Web HTML Elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements)

---

## Tags and Attributes

### Basic Syntax

```html
<tagname attribute="value">Content</tagname>
```

### Example

```html
<a href="https://example.com">Visit site</a>
```

| Part | Example | Purpose |
|------|---------|---------|
| **Tag** | `<a>` | Defines the element type |
| **Attribute** | `href` | Modifies the element |
| **Value** | `"https://example.com"` | Specifies the attribute value |

---

## Case Insensitivity

HTML is **case-insensitive** for tags and attributes. These are all equivalent:

```html
<html>
<HTML>
<Html>
```

**Best Practice:** Use lowercase for better readability and consistency.

```html
<!-- ✅ Good -->
<div class="container">

<!-- ❌ Avoid -->
<DIV CLASS="container">
```

---

## HTML Comments

Comments are notes in your code that don't display in the browser.

### Syntax

```html
<!-- This is a comment -->
```

### Use Cases

```html
<!-- TODO: Add more content here -->
<p>Main content</p>

<!-- Temporarily disabled
<button>Old Button</button>
-->

<!-- This section is for navigation -->
<nav>...</nav>
```

**Note:** Comments are visible in the page source code. Don't use them for sensitive information.

