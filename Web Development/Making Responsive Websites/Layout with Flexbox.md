# Flexbox

Flexible Box Layout or Flexbox is a tool that simplifies positioning of elements.

There are two important components to a flexbox layout:

* flex containers
    This is an element on a page that contains flex items.

* flex items
    All direct child elements of a flex container are flex items.

Some properties apply to containers and others to items.

To designate an element as a flex container we simply set the *display* property to *flex* or *inline-flex*
Then there are several properties we can use to define how its children behave.

### This lesson covers: 

justify-content
align-items
flex-grow
flex-shrink
flex-basis
flex
flex-wrap
align-content
flex-direction
flex-flow

## display: flex;

```CSS
div.container {
  display: flex;
}
```

As mentioned above we make a flex container by setting the display property to flex. In the above example all divs with the class container are now flex containers.

While the div will remain a block element and no other elements will appear on the same line, this is the opposite for its children. Child elements will **not** begin on new lines.

## display: inline-flex;

If we want multiple flex containers on the same line we can use this property.

## justify-content

The default behavior for the flex items is to align to the upper left corner of the container.

the justify-content property allows us to control how flex items align horizontally.

```CSS
.container {
  display: flex;
  justify-content: flex-end;
}
```

### Below are five commonly used values for the justify-content property:

* flex-start — all items will be positioned in order, starting from the left of the parent container, with no extra space between or before them.

* flex-end — all items will be positioned in order, with the last item starting on the right side of the parent container, with no extra space between or after them.

* center — all items will be positioned in order, in the center of the parent container with no extra space before, between, or after them.

* space-around — items will be positioned with equal space before and after each item, resulting in double the space between elements.

* space-between — items will be positioned with equal space between them, but no extra space before the first or after the last elements.

## align-items

this property allows us to control how flex items align vertically.

```CSS
.container {
  align-items: baseline;
}
```
### Below are five commonly used values for the align-items property:

* flex-start — all elements will be positioned at the top of the parent container.

* flex-end — all elements will be positioned at the bottom of the parent container.
center — the center of all elements will be positioned halfway between the top and bottom of the parent container.

* baseline — the bottom of the content of all items will be aligned with each other.

* stretch — if possible, the items will stretch from top to bottom of the container (this is the default value; elements with a specified height will not stretch; elements with a minimum height or no height specified will stretch).

//////////
I don't think these have been covered before so here's a brief explanation for them:

min-height, max-height, min-width, and max-width are properties that ensure an element is at least a certain size or at most a certain size. 
//////////

## flex-grow

By default flex items shrink proportionally when a flex container is too small. However, if the parent container is larger than necessary then flex items will **not** stretch by default. We can ensure this happens with the flex-grow property.

*Note: This property is declared on the flex **items** not on the container!*

```CSS
.container {
  display: flex;
}

.side {
  width: 100px;
  flex-grow: 1;
}

.center {
  width: 100px;
  flex-grow: 2;
}
```
In the example above, the .container div has a display value of flex, so its child divs will be positioned next to each other. If there is additional space in the .container div, the flex items will grow to fill it. The .center div will stretch twice as much as the .side divs. For example, if there were 60 additional pixels of space, the center div would absorb 30 pixels and the side divs would absorb 15 pixels each.

If a max-width is set for an element, it will not grow larger than that even if there is more space for it to absorb.

## flex-shrink

While this is the default behavior and its value is 1 by default we can change this if we want items to shrink in different proportions. Usage is similar to flex-grow but here's an example.

```CSS
.container {
  display: flex;
}

.side {
  width: 100px;
  flex-shrink: 1;
}

.center {
  width: 100px;
  flex-shrink: 2;
}
```

## flex-basis

flex-basis allows us to specify the width of an item before it stretches or shrinks.

```CSS
.container {
  display: flex;
}

.side {
  flex-grow: 1;
  flex-basis: 100px;
}

.center {
  flex-grow: 2;
  flex-basis: 150px;
}
```

In the example above, the .side divs will be 100 pixels wide and the .center div will be 150 pixels wide if the .container div has just the right amount of space (350 pixels, plus a little extra for margins and borders). If the .container div is larger, the .center div will absorb twice as much space as the .side divs.

The same would hold true if we assigned flex-shrink values to the divs above as well.

# flex

The flex property allows to declare flex-grow, flex-shrink, and flex-basis all in one line in the same order.

```CSS
.big {
  flex: 2 1 150px;
}

.small {
  flex: 1 2 100px;
}
```
This declares all three on the same line but what if we want only 2? We can ommit flex-basis or flex-shrink.

```CSS
.small {
  flex: 1 20px;
}
```
In the example above, we use the flex property to declare flex-grow and flex-basis. 
***Unfortunately, there is no way to set only flex-shrink and flex-basis using 2 values.***

## flex-wrap

Sometimes, we don’t want our content to shrink to fit its container. Instead, we might want flex items to move to the next line when necessary. This is what flex-wrap allows us to do.

### It can accept three values:

- wrap — child elements of a flex container that don’t fit into a row will move down to the next line

- wrap-reverse — the same functionality as wrap, but the order of rows within a flex container is reversed (for example, in a 2-row flexbox, the first row from a wrap container will become the second in wrap-reverse and the second row from the wrap container will become the first in wrap-reverse)

- nowrap — prevents items from wrapping; this is the default value and is only necessary to override a wrap value set by a different CSS rule.

```CSS
.container {
  display: inline-flex;
  flex-wrap: wrap;
  width: 250px;
}

.item {
  width: 100px;
  height: 100px;
}
```

In the example above, three flex items are contained by a parent flex container. The flex container is only 250 pixels wide so the three 100 pixel wide flex items cannot fit inline. The flex-wrap: wrap; setting causes the third, overflowing item to appear on a new line, below the other two items.

## align-content

If a flex container has multiple rows of content, we can use align-content to space the rows from top to bottom.

### Below are some of the more commonly used align-content values:

* flex-start — all rows of elements will be positioned at the top of the parent container with no extra space between.

* flex-end — all rows of elements will be positioned at the bottom of the parent container with no extra space between.

* center — all rows of elements will be positioned at the center of the parent element with no extra space between.

* space-between — all rows of elements will be spaced evenly from the top to the bottom of the container with no space above the first or below the last.

* space-around — all rows of elements will be spaced evenly from the top to the bottom of the container with the same amount of space at the top and bottom and between each element.

* stretch — if a minimum height or no height is specified, the rows of elements will stretch to fill the parent container from top to bottom (default value).

```CSS
.container {
  display: flex;
  width: 400px;
  height: 400px;
  flex-wrap: wrap;
  align-content: space-around;
}

.child {
  width: 150px;
  height: 150px;
}
```
In the example above, assume there are four flex items set to be 150 pixels wide each, but the parent container is only 400 pixels wide resulting in no more than 2 items in the same row. 
The align-content property is set to the value of space-around making the two rows of divs evenly spaced from top to bottom of the parent container with equal space before the first row and after the second, with double space between the rows.

# flex-direction

## Axis

Flex containers have 2 axis: main axis which is horizontal and cross axis which is vertical.

### The main axis is used to position flex items with the following properties:

* justify-content
* flex-wrap
* flex-grow
* flex-shrink

### The cross axis is used to position flex items with the following properties:

* align-items
* align-content

## Using flex-direction property

The main axis and cross axis are interchangeable. We can switch them using the flex-direction property. If we add the flex-direction property and give it a value of column, the flex items will be ordered vertically, not horizontally.

```CSS
.container {
  display: flex;
  flex-direction: column;
  width: 1000px;
}
.item {
  height: 100px;
  width: 100px;
}
```

In the example above, the divs will be positioned in a vertical column. The column value tells the browser to stack the divs one on top of the other instead of horizontally. 

### The flex-direction property can accept four values:

* row — elements will be positioned from left to right across the parent element starting from the top left corner (default).

* row-reverse — elements will be positioned from right to left across the parent element starting from the top right corner.

* column — elements will be positioned from top to bottom of the parent element starting from the top left corner.

* column-reverse — elements will be positioned from the bottom to the top of the parent element starting from the bottom left corner.

# flex-flow

Like the shorthand flex property, the shorthand flex-flow property is used to declare both the flex-wrap and flex-direction properties in one line.

Note: The flex-flow property is declared on flex ***containers***.

```CSS
.container {
  display: flex;
  flex-flow: column wrap;
}
```

The first value is the *flex-direction* property and second one is the *flex-wrap* property.

## Nested Flexboxes

So far, we’ve had multiple flex containers on the same page to explore flex item positioning. It is also possible to position flex containers inside of one another.

This is easier to understand if I include the HTML code this time.

```HTML
<div class='container'>
  <div class='left'>
    <img class='small' src='#'/>
    <img class='small' src='#'/>
    <img class='small' src='#' />
  </div>
  <div class='right'>
    <img class='large' src='#' />
  </div>
</div>
```

```CSS
.container {
  display: flex;
  justify-content: center;
  align-items: center;
}

.left {
  display: inline-flex;
  flex: 2 1 200px;
  flex-direction: column;
}

.right {
  display: inline-flex;
  flex: 1 2 400px;
  align-items: center;
}

.small {
  height: 200px;
  width: auto;
}

.large {
  height: 600px; 
  width: auto;
}
```

So in this example there's "container" div as the parent element with "left" and "right" as its children. They themselves have the children "small" and "large".

With the CSS rules we declare that the div with three smaller images will display from top to bottom on the left of the page (.left). There is also a div with one large image that will display on the right side of the page (.right). The left div has a smaller flex-basis but stretches to fill more extra space; the right div has a larger flex-basis but stretches to fill less extra space. Both divs are flex items and flex containers. The items have properties that dictate how they will be positioned in the parent container and how their flex item children will be positioned in them.


# SUMMARY

I'll be adding these from now on as it'll make it a bit easier to find things in my notes. Might go back and add summaries to previous notes too.

* display: flex changes an element to a block-level container with flex items inside of it.

* display: inline-flex allows multiple flex containers to appear inline with each other.

* justify-content is used to space items along the main axis.

* align-items is used to space items along the cross axis.

* flex-grow is used to specify how much space (and in what proportions) flex items absorb along the main axis.

* flex-shrink is used to specify how much flex items shrink and in what proportions along the main axis.

* flex-basis is used to specify the initial size of an element styled with flex-grow and/or flex-shrink.

* flex is used to specify flex-grow, flex-shrink, and flex-basis in one declaration.

* flex-wrap specifies that elements should shift along the cross axis if the flex container is not large enough.

* align-content is used to space rows along the cross axis.

* flex-direction is used to specify the main and cross axes.

* flex-flow is used to specify flex-wrap and flex-direction in one declaration.

* Flex containers can be nested inside of each other by declaring display: flex or display: inline-flex for children of flex containers.