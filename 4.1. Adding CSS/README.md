# CSS Styling Methods Demo

    1.Inline CSS
    2.Internal CSS
    3.External CSS

# Project Files

    index.html
    inline.html
    internal.html
    external.html
    style.css

1. Inline CSS

    File: inline.html
    CSS is written inside the HTML element using the style attribute.

    Example:
    <h1 style="color: aqua;">Style Me in Blue!</h1>

    Notes:
    Applies to a single element
    Highest priority
    Not recommended for large projects

2. Internal CSS

    File: internal.html
    CSS is written inside a <style> tag in the <head> section.

    Example:
    <style> h1 { color: red; } </style>

    Notes:

    Applies to the entire page
    Good for small projects
    Not reusable across multiple pages

3. External CSS

    Files: external.html, style.css
    CSS is stored in a separate file and linked to the HTML file.

    Linking Syntax:
    <link rel="stylesheet" href="./style.css">

    CSS Example:
    h1 {
    color: green;
    }

    Notes:
    Best practice
    Reusable across multiple pages
    Easy to maintain


# CSS Priority Order

    1.Inline CSS
    2.Internal CSS
    3.External CSS

    Higher priority styles override lower priority styles.


# Reference
    MDN Web Docs
    https://developer.mozilla.org/
