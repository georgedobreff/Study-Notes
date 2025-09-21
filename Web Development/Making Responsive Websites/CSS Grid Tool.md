The grid can be used to layout entire web pages. Whereas Flexbox is mostly useful for positioning items in a one-dimensional layout, CSS grid is most useful for two-dimensional layouts, providing many tools for aligning and moving elements across both rows and columns.

# Creating a Grid

To set up a grid we need both a *grid container* and *grid items*. Container is the parent of all items and applies styling and positioning to them.

To turn an HTML element into a grid container, set the element’s display property to one of two values:

grid — for a block-level grid.
inline-grid — for an inline grid.

## Creating Columns

By default grids contain only 1 column.
We can define the columns of our grid by using the CSS property grid-template-columns.
```CSS
.grid {
  display: grid;
  width: 500px;
  grid-template-columns: 100px 200px;
}
```

This property creates two changes. First, it defines the number of columns in the grid; in this case, there are two. Second, it sets the width of each column. The first column will be 100 pixels wide and the second column will be 200 pixels wide.
We can also define the size as a % of the entire grid's width.
These can also be mixed and matched.

## Creating Rows

Basically the same as the columns but for rows. grid-template-rows

```CSS
.grid {
  display: grid;
  width: 1000px;
  height: 500px;
  grid-template-columns: 100px 200px;
  grid-template-rows: 10% 20% 600px;
}
```

## Grid Template

Shorthand for both rows and columns in that order and we separate them with a "/".

```CSS
.grid {
  display: grid;
  width: 1000px;
  height: 500px;
  grid-template: 200px 200px / 50% 50%;
}
```
This will make 2 rows of 200px and 2 columns each 50% of the grid.

# Fraction - fr

The fraction unit (fr) allows us to define the size as a fraction of the grid's length and width.

```CSS
.grid {
  display: grid;
  width: 1000px;
  height: 400px;
  grid-template: 2fr 1fr 1fr / 1fr 3fr 1fr;
}
```
In this example the grid will have 3 rows and 3 columns. Rows split up the defined 400px height into 4 parts with 2 parts assigned to the first row and the others split between the other rows.
Similarly, the columns take the available 1000px width and split it into 5 with 3 parts going to the second column.

Just like any other unit we can mix fr with px or % etc.

# Repeat

The properties that define the number of rows and columns in a grid can take a function as a value. repeat() is one of these functions. The repeat() function was created specifically for CSS Grid.

```CSS
.grid {
  display: grid;
  width: 300px;
  grid-template-columns: repeat(3, 100px);
}
```

This function duplicates the specified size by the given number of times. In this example the repeat function will create 3 columns each 100px wide. This helps write less code while achieving the same results.

The size parameter can have multiple values.So if we want to make 4 columns with 2 of 20px width and 2 of 50px width we can do this with the following:
```CSS
grid-template-columns: repeat(2, 20px 50px)
```

This can be applied to the grid-template shorthand as well. Exmaple:
```CSS
.grid {
  display: grid;
  width: 400px;
  height: 500px;
  grid-template: repeat(3, 1fr) / 3fr 50% 1fr;
}
```
# minmax

Sometimes we want a grid to resize based on the browser size. The minmax() function allows us to do this.

```CSS
.grid {
  display: grid;
  grid-template-columns: 100px minmax(100px, 500px) 100px;
}
```

In this example, the first and third columns will always be 100 pixels wide, no matter the size of the grid. The second column, however, will vary in size as the overall grid resizes. The second column will always be between 100 and 500 pixels wide.

# Grid Gap

The properties row-gap and column-gap will put whitespace between every row and column in the grid.

```CSS
.grid {
  display: grid;
  width: 320px;
  grid-template-columns: repeat(3, 1fr);
  column-gap: 20px;
  row-gap: 10px;
}
```
These properties do ***not*** add space at the beginnning and end of the grid, only between the rows/columns.

## gap

Of course there's a shorthand property for this.It takes value for row-gap followed by column-gap. 
Using the same example as above but with shorthand:
```CSS
.grid {
  display: grid;
  width: 320px;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px 10px;
}
```

# Grid Items

<img src="/Web Development/Making Responsive Websites/Resources/grid-items.svg">

When explicitly defining a grid, you have to declare the quantity of rows and columns and their respective sizes. So far in the examples items have always taken up 1 square. This doesn't have to be the case as seen in the image above.Items A, B, C, and E span more than one row!

## Multiple Row Items

We can use grid-row-start and grid-row-end to define how many rows the items will take.

**Important!** This is declared on the *ITEMS* inside the grid not on the container.

```CSS
.item {
  grid-row-start: 1;
  grid-row-end: 3;
}
```
The values that these properties accept are grid lines. So in the above example the .item will occupy 2 rows starting with 1 and ending on 2 or at the start of the third grid line.
For example if a grid has 5 rows it will have 6 row lines 1-6.

The value for grid-row-start should be the row you want the item to begin at. The value for grid-row-end should be 1 greater than the row you want it to end on.

An element that covers rows 2, 3, and 4 should have these declarations: grid-row-start: 2 and grid-row-end: 5.

The <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/grid-row-start" target="_blank"> documentation </a> has more on this.

### Grid Row

Shorthand for grid-row-start and grid-row-end. Values separated by a "/".
```CSS
.item {
  grid-row: 4 / 6;
}
```

## Grid Column

*grid-column-start* and *grid-column-end* work exactly the same way as the grid row properties so we skip straight to the shorthand for them - *grid-column*.

We can also use the *span* keyword to avoid miscalculated end lines. If we add span we simply define how many columns or rows the item should occupy without worrying about the end line.

```CSS
.item {
  grid-column: 4 / span 2;
}
```

## Grid Area

This property will set the starting and end positions for both rows and columns.

```CSS
.item {
  grid-area: 2 / 3 / 4 / span 5;
}
```

### grid-area takes four values separated by slashes. This is how grid-area will interpret those values. The order is important!

1. grid-row-start
1. grid-column-start
1. grid-row-end
1. grid-column-end

So in the example above the item will start on row 2 and column 3. It will end on row 4 and occupy 5 columns(ending on column line 8 if we didn't use *span*).

**IMPORTANT!** AGAIN the order of the values is always like outlined above! Row and Column START followed by Row and Column END.


# SUMMARY

* grid-template-columns defines the number and sizes of the columns of the grid

* grid-template-rows defines the number and sizes of the rows of the grid

* grid-template is a shorthand for defining both grid-template-columns and grid-template-rows in one line

* row-gap puts blank space between the rows of the grid

* column-gap puts blank space between the columns of the grid

* gap is a shorthand for defining both row-gap and column-gap in one line

* grid-row-start and grid-row-end makes elements span certain rows of the grid

* grid-column-start and grid-column-end makes elements span certain columns of the grid

* grid-area is a shorthand for grid-row-start, grid-column-start, grid-row-end, and grid-column-end, all in one line

