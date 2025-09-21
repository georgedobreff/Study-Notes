Grid systems help organize designs and provide a series of guidelines to properly align elements on a page. Using this visual layout system can help easily define the space needed between elements, while creating content that guides the user on how to navigate the web page.

# Grid Types

The most common type of grid for web design is the column grid. It breaks up a page into vertical units that span the width of the content.

<img src="/Web Development/Making Responsive Websites/Resources/12column-grid.svg">

# Grid Anatomy

<img src="/Web Development/Making Responsive Websites/Resources/grid-anatomy.svg">

The grid comprises of three major components:

* columns

Vertical sections that span the width of a page. It's common to use 12 or 16 columns while some mighty have only 3. Defining the number of columns depends on what's appropriate for the design, device and screen size.

* gutters

This is the negative space between each column.

* margins

These are on the left and right of the whole grid and ensure the content doesn't reach the edges of the window. They can also vary depending on screen size and device.

## Grid Columns

The vertical containers can be dependent on each other or independent of each other. Content can span multiple columns and we can maintain this layout if we choose to.

Columns can also be useful to push/offset content.

## Grid Rows

Rows are invisible and group content together by height. Let's say we have items that span multiple columns and we want to align them across the page without being disrupted by other items. We can do this by wrapping the content in a row component.
This then forces any content outside the row to be pushed away.

## Grid Gutters

There will always be one less gutter than the total number of columns. For example, a 12 column grid will only have 11 gutters, one for every gap that separates each column.

There's no set standard on the gutter size but it just needs to make sense visually. Definitely has to be a lot thinner than the columns.

## Responsive Grid

<img src="/Web Development/Making Responsive Websites/Resources/responsive_grid.webp">

We need to consider different devices and screen sizes when setting out the grid layout. By adjusting the number of columns we can ensure that content is displayed properly on all screens.


# Whitespace

Refers to the space between elements, whether that's the gutter or additional padding. We use this to create a balanced look and it's important to take advantage of it.

There are two types of whitespace - passive and active.

<img src="/Web Development/Making Responsive Websites/Resources/whitespace.svg">

## Passive Whitespace

This is used to improve the aesthetics of the layout without guiding the user through a specific flow. Most frequent use of this is in text elements.
Different fonts have different amounts of passive whitespace and we control that with the line-height or margin properties.

## Active Whitespace

This is when we intentionally separate elements to help guide the user more naturally. For example, we might push footer element down a bit so it separates naturally from the rest of the content. We might add extra padding between rows to help visually differentiate different sections of the content.