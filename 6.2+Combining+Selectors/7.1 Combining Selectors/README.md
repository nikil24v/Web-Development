# 1. Grouping Selector (`,`)

## Explanation  
The grouping selector is used to apply the **same CSS rules to multiple selectors at the same time**.  
This helps reduce repeated code and keeps styles clean and maintainable.

## Syntax
```css
selector1, selector2, selector3 {
  property: value;
}

Example
h1, h2, p {
  color: blue;
}

Meaning

All <h1>, <h2>, and <p> elements will be styled with blue text.

2. Descendant Selector (Space)

Explanation
The descendant selector selects elements that are inside another element at any depth, not just direct children.

Syntax
parent descendant {
  property: value;
}

div p {
  color: green;
}

Meaning
All <p> elements that are anywhere inside a <div> will turn green.

3. Child Selector (>)

Explanation
The child selector selects elements that are only one level down from a parent (direct children only).

parent > child {
  property: value;
}

div > p {
  color: red;
  
}

Meaning
Only <p> elements that are direct children of <div> will turn red.

3. Descendant Selector (Space)
.box li {
  color: blue;
}

Explanation

This is a descendant selector. It selects elements that are inside another element at any level.

Meaning

All <li> elements that appear anywhere inside an element with class box will be styled.

4. Chained Selector (No Space)
li.done {
  color: green;
}


Explanation
This is a chained selector. It applies multiple conditions to the same element.

Meaning
Only <li> elements that also have the class done will be styled.

HTML Example
<li class="done">Styled</li>   <!-- YES -->
<li>Not Styled</li>           <!-- NO -->

5. Multiple Combiners
ul p.done {
  font-size: 0.5rem;
}

Explanation

This rule combines descendant selection and chaining.

Breakdown

ul → ancestor element

p → descendant element

.done → class condition applied to p

Meaning

Selects <p> elements that:

Have the class done

Are located inside a <ul>

HTML Example
<ul>
  <li>
    <p class="done">Styled</p>   <!-- YES -->
  </li>
</ul>
