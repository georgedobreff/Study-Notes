# Positioning Elements

The default position of an element can be changed by setting its position property. The position property can take one of five values:
* Static
    The default value and doesn't need to be specified
* Relative
    Positions an element relative to its normal document flow placement.
* Absolute
    Places an element relative to its nearest positioned ancestor or the browser window.
* Fixed
    Positions an element relative to the viewport, removing it from the document flow and keeping it fixed during page scrolling.
* Sticky
    Defines an element that toggles between relative and fixed positions depending on the scroll position. It becomes sticky on scroll.

## Position: Relative
Diving in a bit deeper into each of these, starting with Relative.

By defalt *"postion:relative;"* sets the element's position relative to its static position on the site. However if we add one or more *offset properties* that will move the element away from its default static position. These offset properties are:

* top
Sets the distance of an element from the top down of the specified position.In other words, moves it down from the top by set amount.
* bottom
Sets the distance of an element from the bottom up of the specified position.
* left
The distance of an element from the left.
* right
The distance of an element from the right.

### Example:

```CSS
.box {
  position: relative;
  top: 50px;
  left: 120px;
}
```
## Position: Absolute

When an element’s position is set to *absolute*, all other elements on the page will ignore the element and act like it is not present on the page.The element gets position by default *relative* to its closes *ancestor* which has a poistion set to anything other than static.
Offset properties can be used with the *absolute* property too.

## Position: Fixed

We can anchor an element to a specific position on the page (regardless of user scrolling) by setting its position to *fixed*. Offset properties are still applicable.

Example:
```CSS
.title {
  position: fixed;
  top: 0px;
  left: 0px;
}
```

## Position: Sticky

Sticky is another position value that keeps an element in the document flow as the user scrolls, but sticks to a specified position as the page is scrolled further.

Example:
```CSS
.box-bottom {
  position: sticky;
  top: 240px;
}
```


# Z Index

Boxes can overlap with each other, making the content difficult to read (and ugly). *z-index* controls how far back or how far forward an element appears aka the depth of the element. It accepts integer values. It does **NOT** work on *static* elements. If the z-index is not declared the default value assumed is 0.

Example:
```CSS
    .blue-box {
    background-color: blue;
    position: relative;
    z-index: 1;
    }
```

# Display Property

## Display: Inline

Elements have a default *display* value that dictates if the horizontal space of the element can be shared with other elements. 
Some elements fill the entire browser space regardless of the size of their content. Others take up just the space they require.

For some elements (eg "em" ; "strong"; "a") the default *display* value is *inline*.
Inline elements take up only the amount of space needed to fit the content of the element and don't require a  new line after each element.

**!!!** The height and width of these elements can **NOT** be speciied in CSS.**!!!**

```HTML
    <a href="https://developer.mozilla.org/en-US/docs/Glossary/Inline-level_content"> MDN Documentation: Inline Content </a>
```

The CSS *display* property allows us to make any element an inline element.

## Display: Block

The elements that are not displayed on the same line are called block-level elements. They fill the entire width of the page by default but we can also change their width property. The default height is what's necessary to accomodate the content.
Some elements that are block-level by default include all heading elements, paragraph, div and footer.
The full list can be found in the documentation.
```HTML
    <a href="https://developer.mozilla.org/en-US/docs/Glossary/Block-level_content">MDN Documentation: Block-Level Content </a>
```

## Display: Inline-Block

Combines inline and block-level features. Inline elements can appear next to each other like blocks and we can modify their width and height properties.
Images are by default inline-block elements.

Example of usage:

- Let's make some divs

```HTML
    <div class="rectangle">
        <p>I’m a rectangle!</p>
    </div>
    <div class="rectangle">
        <p>So am I!</p>
    </div>
    <div class="rectangle">
        <p>Me three!</p>
    </div>
```
- Now let's make them appear next to each other in blocks of 200x300 pixels regardless of the content size.

```CSS
    .rectangle {
        display: inline-block;
        width: 200px;
        height: 300px;
    }
```

# Float
```CSS
    .class {
        width: 50px;
        float:left;
        float:right;
    }
```
If we just want to move an element to the far left or far right of the container we can use the float property. This works for static or relative positions.
The float elements must have their width property defined.

# Clear

This property is used to specify how multiple floating elements should behave when they bump into each other.
Values can be:

* left 
    the left side of the element will not touch any other element within the same containing element.
* right 
    the right side of the element will not touch any other element within the same containing element.
* both 
    neither side of the element will touch any other element within the same containing element.
* none 
    the element can touch either side.
