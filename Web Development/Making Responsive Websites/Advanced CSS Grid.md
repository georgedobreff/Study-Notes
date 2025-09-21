# Grid Template Areas

grid-template-areas

This property allows us to name sections of the page to use as values in the grid-row-start, grid-row-end, grid-column-start,grid-column-end, and grid-area properties. 
This is declared on grid ***containers***.

Example with HTML and CSS:

```HTML
<div class="container">
  <header>Welcome!</header>
  <nav>Links!</nav>
  <section class="info">Info!</section>
  <section class="services">Services!</section>
  <footer>Contact us!</footer>
</div>
```

```CSS
.container {
  display: grid;
  max-width: 900px;
  position: relative;
  margin: auto;
  grid-template-areas: "header header"
                       "nav nav" 
                       "info services"
                       "footer footer";
  grid-template-rows: 300px 120px 800px 120px;
  grid-template-columns: 1fr 3fr; 
}

header {
  grid-area: header;
} 

nav {
  grid-area: nav;
} 

.info {
  grid-area: info;
} 

.services {
  grid-area: services;
}

footer {
  grid-area: footer;
} 
```

Here's what this example does:

The HTML creates a web page with five distinct parts.
In the .container ruleset, the grid-template-areas declaration creates a 2-column, 4-row layout.
The grid-template-rows declaration specifies the height of each of the four rows from top to bottom: 300 pixels, 120 pixels, 800 pixels, and 120 pixels.
The grid-template-columns declaration uses the fr value to cause the left column to use one fourth of the available space on the page and the right column to use three-fourths of the available space on the page.
In each ruleset below .container, we use the grid-area property to tell that section to cover the portion of the page specified. The header element spans the first row and both columns. The nav element spans the second row and both columns. The element with class .info spans the third row and left column. The element with class .services spans the third row and right column. The footer element spans the bottom row and both columns.

# Overlapping Elements

When overlapping elements, it is generally easiest to use the grid-area property with grid row names.

```HTML
<div class="container">
  <div class="info">Info!</div> 
  <img src="#" />
  <div class="services">Services!</div>
</div>
```

```CSS
.container {
  display: grid;
  grid-template: repeat(8, 200px) / repeat(6, 100px);
}

.info {
  grid-area: 1 / 1 / 9 / 4;
}

.services {
  grid-area: 1 / 4 / 9 / 7;
}

img {
  grid-area: 2 / 3 / 5 / 5;
  z-index: 5;
}
```

In the example above, there is a grid container with eight rows and six columns. There are three grid items within the container — a <div> with the class info, a <div> with the class services, and an image.
The info section covers all eight rows and the first three columns. The services section covers all eight rows and the last three columns.
The image spans the 2nd, 3rd, and 4th rows and the 3rd and 4th columns.
The z-index property tells the browser to render the image element on top of the services and info sections so that it is visible.

# Justify Properties

## Justify Items

This property positions grid items along the inline, or row, axis. This means that it positions items from left to right across the web page. This property is declared on grid ***containers***.

### justify-items accepts these values:

* start — aligns grid items to the left side of the grid area

* end — aligns grid items to the right side of the grid area

* center — aligns grid items to the center of the grid area

* stretch — stretches all items to fill the grid area

There are a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/justify-items#Values" target="_blank">few more values</a> it can accept that won't be covered in this lesson.

```CSS
main {
  display: grid;
  grid-template-columns: repeat(3, 400px);
  justify-items: center;
}
```

## Justify Content

We can use justify-content to position the entire grid along the row axis. Also declared on grid ***containers***.

### It accepts these values:

* start — aligns the grid to the left side of the grid container

* end — aligns the grid to the right side of the grid container

* center — centers the grid horizontally in the grid container

* stretch — stretches the grid items to increase the size of the grid to expand horizontally across the container

* space-around — includes an equal amount of space on each side of a grid element, resulting in double the amount of space between elements as there is before the first and after the last element

* space-between — includes an equal amount of space between grid items and no space at either end

* space-evenly — places an even amount of space between grid items and at either end

Again, there are a <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content#Values" target="_blank">few more values</a> it can accept that won't be covered in this lesson.

```CSS
main {
  display: grid;
  width: 1000px;
  grid-template-columns: 300px 300px;
  grid-template-areas: "left right"; 
  justify-content: center;
}
```

# Align Properties

## Align Items

A property that positions grid items along the block, or column axis. This means that it positions items from top to bottom. This property is declared on grid containers.

### align-items accepts these values:

* start — aligns grid items to the top side of the grid area

* end — aligns grid items to the bottom side of the grid area

* center — aligns grid items to the center of the grid area

* stretch — stretches all items to fill the grid area

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/align-items#values" target="_blank">More values</a> it can accept.

```CSS
main {
  display: grid;
  grid-template-rows: repeat(3, 400px);
  align-items: center;
}
```
## Align Content

 Positions the rows along the column axis, or from top to bottom, and is declared on grid containers.

### It accepts these positional values:

* start — aligns the grid to the top of the grid container

* end — aligns the grid to the bottom of the grid container

* center — centers the grid vertically in the grid container

* stretch — stretches the grid items to increase the size of the grid to expand vertically across the container

* space-around — includes an equal amount of space on each side of a grid element, resulting in double the amount of space between elements as there is before the first and after the last element

* space-between — includes an equal amount of space between grid items and no space at either end

* space-evenly — places an even amount of space between grid items and at either end

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/align-content#Values" target="_blank">More values</a> it can accept.



# Justify Self & Align Self

These properties are declared on grid ***items***. 

***justify-self*** overwrites justify-items and specifies how an element should position itself with respect to the row axis.

***align-self*** overwrites align-items and specifies how an element should position itself with respect to the column axis.

### Both accept these four properties:

* start — positions grid items on the left side/top of the grid area

* end — positions grid items on the right side/bottom of the grid area

* center — positions grid items on the center of the grid area

* stretch — positions grid items to fill the grid area (default)


# Implicit vs. Explicit Grid

Explicit grids like the ones in the examples so far are great when we know exactly how much content we'll have on a page. However, in some cases we don't know that and the content can change over time (for example e-commerce sites). In that case we can make *implicit grids*.

The implicit grid is an algorithm built into the specification for CSS Grid that determines default behavior for the placement of elements when there are more than fit into the grid specified by the CSS.

The default behavior of the implicit grid is as follows: items fill up rows first, adding new rows as necessary. New grid rows will only be tall enough to contain the content within them.

## Grid Auto Rows & Colums

grid-auto-rows specifies the height of implicitly added grid rows. grid-auto-columns specifies the width of implicitly added grid columns.

Example:

```HTML
<body>
  <div>Part 1</div>   
  <div>Part 2</div>
  <div>Part 3</div>
  <div>Part 4</div>
  <div>Part 5</div>
</body>
```

```CSS
body {
  display: grid;
  grid: repeat(2, 100px) / repeat(2, 150px); 
  grid-auto-rows: 50px;
}
```
There are 5 <div>s. However, in the body ruleset, we only specify a 2-row, 2-column grid — four grid cells.

The fifth <div> will be added to an implicit row that will be 50 pixels tall. If we did not specify grid-auto-rows, the rows would be auto-adjusted to the height of the content of the grid items.

## Grid Auto Flow

Specifies whether new elements should be added to rows or columns, and is declared on grid containers.

### Accepts these values:

* row — specifies the new elements should fill rows from left to right and create new rows when there are too many elements (default)

* column — specifies the new elements should fill columns from top to bottom and create new columns when there are too many elements

* dense — this keyword invokes an algorithm that attempts to fill holes earlier in the grid layout if smaller elements are added

We can pair row or column with dense, like this: ```grid-auto-flow: row dense;```

Example:

```HTML
<body>
    <div class='box'>Part 1</div>   
    <div class='box'>Part 2</div>
    <div class='box'>Part 3</div>
    <div class='box'>Part 4</div>
    <div class='box'>Part 5</div>
</body>
```

```CSS
body {
  display: grid;
  gap: 5px;
  grid: repeat(2, 100px) / repeat(2, 150px);
  grid-auto-rows: 45px;
  grid-auto-columns: 65px;
  grid-auto-flow: column;
}
```

The output will look like this:

<img src="/Web Development/Making Responsive Websites/Resources/auto-flow-example.png">

The fifth grid item is added to a new, implicit column. The width of this implicit column is dictated by grid-auto-columns, making the fifth item 65px wide — narrower than the other grid items.
With *grid-auto-flow: column* added to the grid, new items will be added to the existing, explicitly defined rows. Because of this, new items will have the same height as all the items within the explicit grid, 100px, as defined by the grid property.

# SUMMARY

* grid-template-areas specifies grid named grid areas

* grid layouts are two-dimensional: they have a row, or inline, axis and a column, or block, axis.

* justify-items specifies how individual elements should spread across the row axis

* justify-content specifies how groups of elements should spread across the row axis

* justify-self specifies how a single element should position itself with respect to the row axis

* align-items specifies how individual elements should spread across the column axis

* align-content specifies how groups of elements should spread across the column axis

* align-self specifies how a single element should position itself with respect to the column axis

* grid-auto-rows specifies the height of rows added implicitly to the grid

* grid-auto-columns specifies the width of columns added implicitly to the grid

* grid-auto-flow specifies in which direction implicit elements should be created