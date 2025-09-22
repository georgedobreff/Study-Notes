# Setup & Syntax

Cascading Style Sheets is a language used to style HTML. Ruleset covers all pages while inline is specific to that particular element.

## Ruleset Terms

Default way to write CSS and usually in a stylesheet.css file.

- Selector - The beginning of the ruleset is used to target the element that will be styled
- Declaration block - The code in-bertween the {} that contains the declarations.
- Declaration - The group name for the property and value pair that applies a style.
- Property - FIrst part of the declaration that signifies what visual characterristic of the element is to be modified.
- Value - The second part of the declaration that signifies the value of the property.

## Inline Style Terms

Written in the HTML if we want to style a specific element. Absolute no no ! 

* Opening tag - tag of the element that's styled
- Attribute - *style* attribute adds CSS styles
- Declaration - Same as Ruleset
- Property - Same as Ruleset

## Internal Stylesheet

Not efficient so a no go. Avoid this.

We can use the ```<style></style>``` element inside ```<head>``` if we want to add Ruleset CSS to the HTML file and create an internal stylesheet.

Just ***don't*** do this.

## External Stylesheet

This is the way to go. A separate .css file that contains the CSS rules.

## Linking the CSS file

The HTML document needs to connect to the .CSS stylesheet and to do this we use the ```<link>``` element and put it inside ```<head>```.
The element takes two arguments:
 - href - this is the path to the file.
 - rel - this describes the relationship between the files and is usually "stylesheet".

 Example:

 ```HTML
 <head>
    <link href='./style.css' rel='stylesheet'>
</head>
```

# Selectors

A selector is used to target specific elements.

## Type Selector
This selector indicates the html element and does not use <>. It's sometimes referred to  as the tag name or element selector.

Example where ***p*** is the selector:
```CSS
p {
    color: red;
}
```

## Universal Selector "*"
As the name sugggests this targets ALL elements of ALL types. For example, if we want to set the font for all elements we can use **"*"**
```CSS
* {
    font-family: Verdana;
}
```

## Class Selector

We can select elements using thir assigned *class* instead. We simply add a dot in front of the class name.
```CSS
.brand {
}
```

## Multiple Classes
HTML elements can have multiple classes separated by space.
```HTML
<h1 class="class 1 class 2 class 3> Classes </h1>
```

Useful for mixing and matching classes to create many unique styles without writing a custom class for every combination.

## ID

Similar to classes we can select the assigned id attribute to an element. WE do this with a #.

```CSS
#title {
    color:red;
}
```

## Attribute Selector

We can also target specific attributes like href or src. We use [].

```CSS
[href]{
    color:red;
}
```
# Pseudo-classes

These are used to change behavior based on user actions. It can be attached to any selector and is written with a ":". like :focus, :visited, :hover, etc.

```CSS
p:hover{
    color:blue;
}
```

## Specificity

 This is the order by which the browser decides which CSS styles will be displayed.
 IDs are the MOST specific selector, followed by classes and finally type.
 
 Best practice is to use the lowest degree of specificity so that if an element needs a new style it is easy to overwrite.

 ## Chaining
 
We can combine two or more selectors at the same time which allows us to get even more specific in our styling rules. For example:

```CSS
h1.special{   
}
```
This would target only the h1 elements that have class 'special'.
If another element (like a paragraph) also has the same class it will not be affected by this rule.

## Descendant Combinator

We can also target nested elements. For example we can target an ```<ul>``` with a class of 'main-list' and more specifically the ```<li>``` inside it. Example:

```CSS
.main-list li {
}
```

## Multiple Selectors

If we need to apply the same CSS rules to multiple selectors we can combine them in one to keep the code neat and readable.
For example, instead of writing two sets for h1 and a class 'menu' we do:

```CSS
h1,
.menu {
    color:red;
}
```


# Visual Rules

## Font Family

```CSS
h1 {
  font-family: Garamond;
}
```
In the example above, the font family for all main heading elements has been set to Garamond.

When setting typefaces on a web page, keep the following points in mind:

- The font specified must be installed on the user’s computer or downloaded with the site.
- Web safe fonts are a group of fonts supported across most browsers and operating systems.
- Unless you are using web safe fonts, the font you choose may not appear the same between all browsers and operating systems.
- When the name of a typeface consists of more than one word, it’s a best practice to enclose the typeface’s name in quotes, like so:

```CSS
h1 {
  font-family: 'Courier New';
}
```

## Font Size

```CSS
p {
  font-size: 18px;
}
```

In the example above, the font-size of all paragraphs was set to 18px. px means pixels, which is one way to measure font size.


## Font Weight

The font-weight property controls how bold or thin text appears.

```CSS
p {
  font-weight: bold;
}
```
The font-weight property has another value: normal. Why does it exist?

If we wanted all text on a web page to appear bolded, we could select all text elements and change their font weight to bold. If a certain section of text was required to appear normal, however, we could set the font weight of that particular element to normal, essentially shutting off bold for that element.

## Text Align

No matter how much styling is applied to text it always appears on the left side of the container in which it resides. To change this the text-align property can be used to align text to the element that holds it, otherwise known as its parent.

```CSS
h1 {
  text-align: right;
}
```

### The text-align property can be set to one of the following commonly used values:

* left — aligns text to the left side of its parent element, which in this case is the browser.

* center — centers text inside of its parent element.

* right — aligns text to the right side of its parent element.

* justify— spaces out text in order to align with the right and left side of the parent element.

## Color and Background Color

```CSS
h1 {
  color: red;
  background-color: blue;
}
```

Color can affect the following design aspects:
- Foreground color
- Background color

These can be styled with the following two properties:

- color : this property styles an element’s foreground color
- background-color: this property styles an element’s background color

## Opacity

```CSS
.overlay {
  opacity: 0.5;
}
```

Opacity is the measure of how transparent an element is. It’s measured from 0 to 1, with 1 representing 100%, or fully visible and opaque, and 0 representing 0%, or fully invisible.

Opacity can be used to make elements fade into others for a nice overlay effect.

## Background Image

```CSS
.main-banner {
  background-image: url('https://www.example.com/image.jpg');
}
```

This property allows us to set the background of an element to an image.

The value provided to background-image is a url. The url should be a URL to an image. The url can be a file within your project, or it can be a link to an external site. 

## Important!

```CSS
p {
  color: blue !important;
}
```

*!important* can be applied to specific declarations, instead of full rules. It will override any style no matter how specific it is. As a result, it should almost never be used. Once !important is used, it is very hard to override.

One justification for using !important is when working with multiple stylesheets. For example, if we are using the <a href="https://getbootstrap.com/" target="_blank">Bootstrap CSS</a> framework and want to override the styles for one specific HTML element, we can use the !important property.

