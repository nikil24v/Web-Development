# 8.2 Flex Direction

## Overview
This lesson teaches how to combine CSS selectors (`container > *`) with flexbox properties to create flexible, responsive layouts. The focus is on understanding **child combinators**, the **universal selector**, and **flex-direction**.

---

## HTML Structure

The `index.html` contains a container with 7 colored divs arranged vertically:

```html
<div class="container">
  <div class="red">Red</div>
  <div class="orange">Orange</div>
  <div class="yellow">Yellow</div>
  <div class="green">Green</div>
  <div class="blue">Blue</div>
  <div class="indigo">Indigo</div>
  <div class="purple">Purple</div>
</div>
```

---

## CSS Concepts & Teaching Points

### 1. **Combined Selector: `.container > *`**

```css
.container > * {
  flex-basis: 100px;
}
```

#### What does `container > *` mean?

- **`.container`** = Selects the element with class "container"
- **`>`** = **Child combinator** - selects ONLY direct children
- **`*`** = **Universal selector** - matches ANY HTML element type

#### Combined meaning:
**"Select ALL direct children of `.container`, regardless of their element type, and apply the styling."**

#### Why use `container > *` instead of other selectors?

| Selector | What it targets | Use case |
|----------|-----------------|----------|
| `.container > *` | All direct children (any type) | When you have mixed elements (divs, spans, p tags, etc.) |
| `.container > div` | Only direct `<div>` children | When you only want to style divs |
| `.container *` | All descendants (children, grandchildren, etc.) | When you want to style nested elements too |
| `.container` | Just the container | When styling the container itself |

#### Advantage:
Without `*`, you'd need to write:
```css
.container > div { flex-basis: 100px; }
.container > span { flex-basis: 100px; }
.container > p { flex-basis: 100px; }
/* ... and so on */
```

With `*`, one single rule handles ALL element types!

---

### 2. **Flex Direction: Column**

```css
.container {
  color: white;
  border: 5px solid gold;
  display: inline-flex;
  flex-direction: column;
}
```

#### What is `flex-direction`?

`flex-direction` controls the **direction** in which flex items are arranged inside a flex container.

#### Available values:

| Value | Direction | Example |
|-------|-----------|---------|
| `row` | Left → Right (default) | [Red] [Orange] [Yellow] |
| `column` | Top → Bottom | [Red] [Orange] [Yellow] (stacked) |
| `row-reverse` | Right → Left | [Yellow] [Orange] [Red] |
| `column-reverse` | Bottom → Top | (reversed vertical) |

#### In this lesson:
```css
flex-direction: column;  /* Items stack VERTICALLY from top to bottom */
```

This transforms the flex container layout to display the colored divs vertically (one below the other) instead of horizontally.

---

### 3. **Flex Basis**

```css
.container > * {
  flex-basis: 100px;
}
```

#### What is `flex-basis`?

`flex-basis` defines the **default/base size** of a flex item before free space is distributed.

- **In row direction**: Sets the default width
- **In column direction**: Sets the default height

#### In this lesson:
```css
flex-basis: 100px;  /* Each colored div gets 100px height (because flex-direction is column) */
```

---

### 4. **Inline-Flex vs Flex**

```css
display: inline-flex;  /* Container behaves as inline element */
```

| Property | Behavior |
|----------|----------|
| `display: flex` | Container takes full width (block-level) |
| `display: inline-flex` | Container only takes space it needs (inline-level) |

---

### 5. **Common Flex Values & What They Mean**

The `flex` property is a shorthand: `flex: [grow] [shrink] [basis]`

Understanding these value combinations helps you control item sizing:

| Value | Breakdown | Meaning |
|-------|-----------|---------|
| `flex: 0 0 1` | grow:0, shrink:0, basis:1 | Fixed 1px, no growth/shrink |
| `flex: 0 0 50px` | grow:0, shrink:0, basis:50px | Fixed 50px, completely rigid |
| `flex: 1 0 0` | grow:1, shrink:0, basis:0 | Grows to fill, doesn't shrink |
| `flex: 1 1 0` | grow:1, shrink:1, basis:0 | Grows & shrinks with equal space |
| `flex: 1 1 100px` | grow:1, shrink:1, basis:100px | Flexible, starts at 100px |
| `flex: 0 1 auto` | grow:0, shrink:1, basis:auto | Doesn't grow, can shrink, content-sized |
| `flex: 1 0 auto` | grow:1, shrink:0, basis:auto | Grows, doesn't shrink, content-sized |
| `flex: 1 1 auto` | grow:1, shrink:1, basis:auto | Fully flexible, content-based start |

#### Important Points About Flex Values:

**Flex-Grow (First Number):**
- `0` = Item doesn't take extra space
- `1` or higher = Item expands proportionally
- Higher number = gets more of the available space

**Flex-Shrink (Second Number):**
- `0` = Item never shrinks, keeps its size (may overflow)
- `1` = Item shrinks equally with others (default)
- Higher number = shrinks more when space is tight

**Flex-Basis (Third Value):**
- Can be `px`, `%`, `em`, or `auto`
- `0` = Ignore content size, use only grow/shrink
- `auto` = Size based on content (default)
- `100px` = Start at 100px, then grow/shrink from there

#### Quick Shortcuts:

```css
flex: 1        /* = flex: 1 1 0 (equal columns, fill space) */
flex: auto     /* = flex: 1 1 auto (flexible, responsive) */
flex: none     /* = flex: 0 0 auto (fixed size) */
flex: initial  /* = flex: 0 1 auto (default, no growth) */
```

#### Real-World Example:

```css
/* Sidebar - fixed width */
.sidebar { flex: 0 0 250px; }

/* Main content - takes remaining space */
.main { flex: 1 1 auto; }

/* Equal columns */
.column { flex: 1; }
```

---

## Color Classes

Each div gets a background color:

```css
.red {background-color: #eb4d4b;}
.orange {background-color: #f0932b;}
.yellow {background-color: #f6e58d;}
.green {background-color: #6ab04c;}
.blue {background-color: #4834d4;}
.indigo {background-color: #30336b;}
.purple {background-color: #be2edd;}
```

---

## Key Learning Outcomes

### ✅ Combined Selectors
- Learned the **child combinator** (`>`) syntax
- Understood how `>` differs from descendant selector (space)
- Combined selectors with the **universal selector** (`*`)
- Applied `container > *` to style all direct children efficiently

### ✅ Flex Direction
- Understood `flex-direction: column` stacks items vertically
- Learned `flex-direction: row` would stack items horizontally
- Saw how flexbox responds to the direction property

### ✅ Flex Basis
- Understood how `flex-basis` sets the base size of flex items
- Saw how `flex-basis: 100px` creates uniform-sized flex children

### ✅ Selector Efficiency
- Learned to use `*` (universal selector) for flexibility
- Avoided writing repetitive CSS rules for multiple element types
- Made code more maintainable and scalable

---

## Visual Result

When you open `index.html` or `solution.html`, you'll see:
- **A vertical stack** of 7 colored boxes (Red, Orange, Yellow, Green, Blue, Indigo, Purple)
- **Each box** is 100px tall (from `flex-basis: 100px`)
- **All aligned** inside a gold-bordered container
- **Arranged vertically** (from `flex-direction: column`)

---

## Practice

Try modifying the CSS:

1. **Change `flex-direction: column` to `flex-direction: row`** → See items arrange horizontally
2. **Change `flex-basis: 100px` to `flex-basis: 50px`** → See items become smaller
3. **Add `justify-content: center`** → See how items align along the main axis
4. **Add `align-items: center`** → See how items align along the cross axis
5. **Replace `.container > *` with `.container > div`** → Still works since all children are divs

---

## MDN References

- [CSS Universal Selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Universal_selectors)
- [CSS Combinators](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Combinators)
- [Flex Direction](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction)
- [Flex Basis](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-basis)
