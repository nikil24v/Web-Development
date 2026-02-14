Explanation of display: flex

display: flex transforms a regular block element into a flex container.

When applied:

All direct children become flex items.

Items are arranged in a row by default.

The layout becomes flexible and responsive.

Alignment and distribution can be controlled using:

justify-content

align-items

flex-direction

flex-wrap

Default Behavior
.container {
display: flex;
}

Direction: row

Items align horizontally

Items size automatically based on content

Container behaves as a block-level element

Flexbox is a one-dimensional layout system (row OR column).

Difference Between flex and inline-flex

display: flex

Takes full width of its parent

Starts on a new line

Behaves like display: block

display: inline-flex

Takes only the width of its content

Can sit next to other inline elements

Behaves like inline-block
