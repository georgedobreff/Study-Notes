# The Box Model

<img src="/Web Development/CSS Fundamentals/Resources/boxmodel.svg">

The box model comprises the set of properties that define parts of an element that take up space on a web page. The model includes the content area’s size (width and height) and the element’s padding, border, and margin. 
### The properties include:
- width and height: The width and height of the content area.
- padding: The amount of space between the content area and the border.
- border: The thickness and style of the border surrounding the content area and padding.
- margin: The amount of space between the border and the outside edge of the element.

## Height and Width

```CSS
p {
  height: 80px;
  width: 240px;
}
```

An element’s content has two dimensions: a height and a 
width
Preview: Docs Defines the width of an element's content area. The content area is the space inside the padding, border, and margin of the element.
By default, the dimensions of an HTML box are set to hold the raw contents of the box.
We use width and height to change this.


## Borders

```CSS
p {
  border: 3px solid coral;
}
```

A border is a line that surrounds an element, like a frame around a painting. 
Borders can be set with a specific width, style, and color:

- width—The thickness of the border. A border’s thickness can be set in pixels or with one of the following keywords: thin, medium, or thick.
- style—The design of the border. Web browsers can render any of 10 different styles. Some of these styles include: none, dotted, and solid.
- color—The color of the border.

The default border is medium none color, where color is the current color of the element. If width, style, or color are not set in the CSS file, the web browser assigns the default value for that property.

### Border Radius

```CSS
div.container {
  border: 3px solid blue;
  border-radius: 5px;
}
```

You can modify the corners of an element’s border box with the border-radius property.

## Padding

```CSS
p.content-header {
  border: 3px solid coral;
  padding: 10px;
}
```

The space between the contents of a box and the borders of a box is known as padding. 
The padding property is often used to expand the background color and make the content look less cramped.

If you want to be more specific about the amount of padding on each side of a box’s content, you can use the following properties:

- padding-top
- padding-right
- padding-bottom
- padding-left

### Padding Shorthand 

```CSS
p.content-header {
  padding: 6px 11px 4px 9px;
}
```
Padding shorthand lets you specify all of the padding properties as values on a single line in this same order:

padding-top padding-right padding-bottom padding-left;


## Margin

```CSS
p {
  border: 1px solid aquamarine;
  margin: 20px;
}
```

Margin refers to the space directly outside of the box. The margin property is used to specify the size of this space.
We can be more specific by setting margin-top;margin-right;margin-bottom or margin-left just like with padding.

### Margin Shorthand

```CSS
p {
  margin: 6px 10px 5px 12px;
}
```

Same as padding we have shorthand and it goes in the same order:
margin-top margin-right margin-bottom margin-left;

If we write only 2 values they will set top and bottom and left and right.

### Margin Collapse

<img src="/Web Development/CSS Fundamentals/Resources/margins.svg">

Top and bottom margins also called vertical margins, collapse, while top and bottom padding does not.Horizontal margins (left and right), like padding, are always displayed and added together. Unlike horizontal margins, vertical margins do not add. Instead, the larger of the two vertical margins sets the distance between adjacent elements.

## Min and Max Height and Width

```CSS
p {
  min-width: 300px;
  max-width: 600px;
  min-width: 300px;
  max-width: 600px;
}
```


CSS offers two properties that can limit how narrow or how wide or tall an element’s box can be sized to:

* min-width — this property ensures a minimum width
* max-width — this property ensures a maximum width of an element’s box.
* min-height — this property ensures a minimum height for an element’s box.
* max-height — this property ensures a maximum height of an element’s box.

## Overflow

The overflow property controls what happens to content that spills, or overflows, outside its box. 

### The most commonly used values are:

```CSS
p {
  overflow: scroll; 
}
```

* hidden—when set to this value, any content that overflows will be hidden from view.
* scroll—when set to this value, a scrollbar will be added to the element’s box so that the rest of the content can be viewed by scrolling.
* visible—when set to this value, the overflow content will be displayed outside of the containing element. Note, this is the default value.

The overflow property is set on a parent element to instruct a web browser on how to render child elements. 

## Resetting Defaults

```CSS
* {
  margin: 0;
  padding: 0;
}
```

All major web browsers have a default stylesheet they use in the absence of an external stylesheet called a user agent stylesheet.
User agent stylesheets often have default CSS rules that set default values for padding and  margin. This affects how the browser displays HTML elements, which can make it difficult for a developer to design or style a web page.

Many developers choose to reset these default values so that they can truly work with a clean slate.

## Visibility

```CSS
.future {
  visibility: hidden;
}
```

Elements can be hidden from view with the visibility property.

### The visibility property can be set to one of the following values:

* hidden — hides an element.
* visible — displays an element.
* collapse — collapses an element.

What’s the difference between display: none and visibility: hidden? An element with display: none will be completely removed from the web page. An element with visibility: hidden, however, will not be visible on the web page, but the space reserved for it will.

# SUMMARY

- The box model comprises a set of properties used to create space around and between HTML elements.
- The height and width of a content area can be set in pixels or percentages.
- Borders surround the content area and padding of an element. The color, style, and thickness of a border can be set with CSS properties.
- Padding is the space between the content area and the border. It can be set in pixels or percent.
- Margin is the amount of spacing outside of an element’s border.
- Horizontal margins add, so the total space between the borders of adjacent elements is equal to the sum of the right 
margin of one element and the left margin of the adjacent element.
- Vertical margins collapse, so the space between vertically adjacent elements is equal to the larger margin.
- margin: 0 auto horizontally centers an element inside of its parent content area, if it has a width.
- The overflow property can be set to display, hidden, or scroll, and dictates how HTML will render content that overflows its parent’s content area.
- The visibility property can hide or show elements.

# Changing the Box Model

The box model has an awkward limitation regarding box dimensions. Border thickness, padding and other properties like this can affect the overall dimensions of the box.
This makes it difficult to accurately size a box. Over time, this can also make all of a web page’s content difficult to position and manage.

## Box Model: Content-Box

<img src="/Web Development/CSS Fundamentals/Resources/contentbox.svg">

In CSS, the box-sizing property controls the type of box model the browser should use when interpreting a web page. The default value is content-box which is the same model that's affected by borders and padding.

## Box Model: Border-Box

<img src="/Web Development/CSS Fundamentals/Resources/borderbox.svg">

We can reset the entire box model and specify a new one: border-box.

```CSS
* {
  box-sizing: border-box;
}
```

This new box model avoids the dimensional issues that exist in the former box model you learned about.
In this box model, the height and width of the box will remain fixed. The border thickness and padding will be included inside of the box, which means the overall dimensions of the box do not change.