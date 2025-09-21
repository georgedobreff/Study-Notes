Devices of different screen sizes, however, pose a problem for web developers: how can we ensure that a website is readable and visually appealing across all devices, regardless of screen size?

The answer: responsive design! Responsive design refers to the ability of a website to resize and reorganize its content based on:

The size of other content on the website.
The size of the screen the website is being viewed on.


# SIZING ELEMENTS

With CSS, we can avoid hard coded measurements and use relative measurements instead. Relative measurements offer an advantage over hard coded measurements, as they allow for the proportions of a website to remain intact regardless of screen size or layout.

## Em

em represents the font-size of the current element or the default base font-size set by the browser if none is given.
For example, if the base font of a browser is 16 pixels, then 1em is equal to 16 pixels. 2em would equal 32 pixels, and so on.

```CSS
.heading {
  font-size: 1.75em;
}
```

## Rem

Rem stands for root em. It acts similar to em, but instead of checking parent elements to size font, it checks the root element. The root element is the <html> tag.

Most browsers set the font size of <html> to 16 pixels, so by default rem measurements will be compared to that value. 

Of course we can change this by adding a rule for the html tag.

```CSS
html {
  font-size: 20px;
}

h1 {
  font-size: 1.875rem;
}
```


## Percentages 

### Height & Width

Percentages are often used to size box-model values, like width and height, padding, border, and margins. They can also be used to set positioning properties (top, bottom, left, right).

```CSS
.main {
  height: 300px;
  width: 500px;
}
 
.main .subsection {
  height: 50%;
  width: 50%;
}
```

When percentages are used, elements are sized relative to the dimensions of their parent element.

### Padding & Margin

Padding and margin are calculated based on the width of the parent, including vertical padding and margin.

## Width: Minimum & Maximum

These two properties ensure that content is legible by limiting the minimum and maximum widths.

min-width — ensures a minimum width for an element.
max-width — ensures a maximum width for an element.

```CSS
p {
  min-width: 300px;
  max-width: 600px;
}
```
The px unit is used to set a hard limit.

## Height: Minimum & Maximum

Similarly, we can use these to set limits on height.

```CSS
p {
  min-height: 150px;
  max-height: 300px;
}
```

## Scaling images and videos

This is better explained with an example and it's worth remembering the entire example as it's very common. We basically set width or height limit to the image/video container and with *overflow: hidden;* we ensure that when the browser is resized the excess becomes invisible rather than overflowing and disturbing the design.
The *max-width: 100%;* and *height: auto;* ensure the whole image is resized with the window.

```CSS
.container {
  width: 50%;
  height: 200px;
  overflow: hidden;
}

.container img {
  max-width: 100%;
  height: auto;
  display: block;
}
```
*.container* is set to a width of 50% and a height of 200 pixels. Setting *overflow* to hidden ensures that any content with dimensions larger than the container will be hidden from view.

The second CSS rule ensures that images scale with the width of the container. The *height* property is set to *auto*, meaning an image’s height will automatically scale proportionally with the width. Finally, the last line will *display* images as *block* level elements (rather than the default inline-block). This will prevent images from attempting to align with other content on the page (like text), which can add unintended margin to the images.


If the image is larger than the container, the vertical portion of the image will overflow and will not display. 
To swap this behavior, set *max-height* to *100%* and *width* to auto (essentially swapping the values). This will scale the height of the image with the height of the container instead. If the image is larger than the container, the horizontal portion of the image will overflow and not display.

## Scaling Background Images

```CSS
body {
  background-image: url('#');
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}
```
The second declaration instructs the CSS compiler to not repeat the image (by default, images will repeat). The third declaration centers the image within the element.
The final declaration, however, is the focus of the example above. It’s what scales the background image. The image will *cover* the entire background of the element, all while keeping the image in proportion. If the dimensions of the image exceed the dimensions of the container then only a portion of the image will display.


## SUMMARY

* Content on a website can be sized relative to other elements on the page using relative measurements.

* The unit of em sizes font relative to the font size of a parent element.

* The unit of rem sizes font relative to the font size of a root element. That root element is the <html> element.

* Percentages are commonly used to size box-model features, like the width, height, padding, or margin of an element.

* When percentages are used to size width and height, child elements will be sized relative to the dimensions of their parent (remember that parent dimensions must first be set).

* Percentages can be used to set padding and margin. Horizontal and vertical padding and margin are set relative to the width of a parent element.

* The minimum and maximum width of elements can be set using min-width and max-width.

* The minimum and maximum height of elements can be set using min-height and max-height.

* When the height of an image or video is set, then its width can be set to auto so that the media scales proportionally. Reversing these two properties and values will also achieve the same result.

* A background image of an HTML element will scale proportionally when its background-size property is set to cover.


# VIEWPORT

## Viewport Meta Tag

*viewport* is the total viewable area for a user; this area varies depending on device.

Based on the size of the viewport, the meta tag (<meta>) is used to instruct the browser on how to render the webpage’s scale and dimensions. 

For example, if a page is 960px wide and the device is 320px wide. Adding the viewport meta tag will squish the content down until it is 320px — there is no need for the user to zoom out and view the whole page.

The <meta> tag goes in the <head>.

```HTML
<!DOCTYPE html> 
<html> 
  <head> 
    ...
    <meta name="viewport" content="width=device-width, initial-scale=1">
    ...
  </head> 
```
### These are the essential components of the tag:

* name="viewport" attribute: tells the browser to display the web page at the same width as its screen

* content attribute: defines the values for the <meta> tag, including width and initial-scale

* width=device-width key-value pair: controls the size of the viewport in which it sets the width of the viewport to equal the width of the device

* initial-scale=1 key-value pair: sets the initial zoom level 

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Guides/Viewport_meta_element#viewport_basics" target="_blank"> Viewport Basics Documentation </a>

# MEDIA QUERIES

With *media queries*, CSS can detect the size of the current screen and apply different CSS styles depending on the width of the screen.

```CSS
@media only screen and (max-width: 480px) {
  body {
    font-size: 12px;
  }
}
```
The above media query defines a rule for screens smaller than 480 pixels.
### Breakdown:

* @media — This keyword begins a media query rule and instructs the CSS compiler on how to parse the rest of the rule.

* only screen — Indicates what types of devices should use this rule. *screen* is the media type always used for displaying content, no matter the type of device. The *only* keyword is added to indicate that this rule only applies to one media type (screen).

* and (max-width : 480px) — This part of the rule is called a media feature, and instructs the CSS compiler to apply the CSS styles to devices with a width of 480 pixels or smaller. Media features are the conditions that must be met in order to render the CSS within a media query.

* CSS rules are then nested inside of the media query’s curly braces. The rules will be applied when the media query is met. In the example above, the text in the body element is set to a font-size of 12px when the user’s screen is less than 480px.

## Range

By using multiple widths and heights, a range can be set for a media query.

```CSS
@media only screen and (min-width: 320px) and (max-width: 480px) {
    /* ruleset for 320px - 480px */
}
```

The rules we add in the above media query will apply only to screen sizes between 320px and 480px. The *and* keyword chains the two requirements together.

This could also be written as two separate queries, and the rules applicable to screens of 480px or more will overwrite the rules for 320px or more.

```CSS
@media only screen and (min-width: 320px) { 
    /* ruleset for >= 320px */
}


@media only screen and (min-width: 480px) { 
    /* ruleset for >= 480px */
}
```

## Dots Per Inch (DPI)

Another media feature we can target is *resolution*. To target by resolution, we can use the *min-resolution* and *max-resolution*.
These accept a resolution value in either dots per inch (dpi) or dots per centimeter (dpc). 
```CSS
@media only screen and (min-resolution: 300dpi) {
    /* CSS for high resolution screens */
}
```

## And Operator


Placing the *and* operator between two media features will require both media features to be true before the browser renders the CSS within the media query. The *and* operator can be used to chain as many media features as necessary.

## Comma Separated List

If we only need to meet one of the media feature requirements we can chain the requirements with a comma ",".

```CSS
@media only screen and (min-width: 480px), (orientation: landscape) {
    /* CSS ruleset */
}
```

In the above example the ruleset will apply if the screen is 480px or more OR the orientation is in landscape.
The *orientation* media feature detects if the page has more width than height. If a page is wider, it’s considered *landscape*, and if a page is taller, it’s considered *portrait*.

## Breakpoints

Breakpoints are the screen sizes at which your web page does not appear properly. 

<img src="/Web Development/Making Responsive Websites/Resources/screen-sizes.webp">


Rather than setting breakpoints based on specific devices, the best practice is to resize your browser to view where the website naturally breaks based on its content. The dimensions at which the layout breaks or looks odd become your media query breakpoints. 

We can do this on a project by project basis. Different projects have different needs, and creating a responsive design should be no different.

## SUMMARY 

* When a website responds to the size of the screen it’s viewed on, it’s called a responsive website.

* You can write media queries to help with different screen sizes.

* Adding the viewport <meta> tag to our code allows us to control the width and scaling of the viewport so that it’s sized and scaled correctly on all devices.

* Media queries require media features. Media features are the conditions that must be met to render the CSS within a media query.

* Media features can detect many aspects of a user’s browser, including the screen’s width, height, resolution, orientation, and more.

* The and operator requires multiple media features to be true at once.

* A comma separated list of media features only requires one media feature to be true for the code within to be applied.

* The best practice for identifying where media queries should be set is by resizing the browser to determine where the content naturally breaks. Natural breakpoints are found by resizing the browser.