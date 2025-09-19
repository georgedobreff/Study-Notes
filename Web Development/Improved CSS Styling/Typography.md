Some of the most important information a user will see on a web page will be textual. Styling text to make page content accessible and engaging can significantly improve user experience.

# Font Family

## Multi-Word Values

When specifying typeface with multiple words it's recommended to use quotation marks ('').
``font-family: 'Times New Roman';``

## Web Safe Fonts

These are fonts that will appear the same across all browsers and devices. A full list can be found <a href="https://www.cssfontstack.com/"> here </a>

## Fallback Fonts and Font Stacks

The web safe fonts are a good fallback in case the preferred font is not available. We specify this with a group of fonts which is called a *font stack*. These are usually similar looking fonts. Preferred font goes first, then the fallback fonts. 
Example:
```CSS
h1 {
  font-family: Caslon, Georgia, 'Times New Roman';
}
```
In this example if Caslon is not available we'll try to use Georgia and if that's not available we'll fallback to Times New Roman.

## Serif and Sans-Serif

Serif fonts have extra details on the ends of each letter, as opposed to Sans-Serif fonts, which do not have the extra details.
*serif* and *sans-serif* are also keyword values that can be added as a final fallback font if nothing else in the font stack is available.
Example:
```CSS
h1 {
  font-family: Caslon, Georgia, 'Times New Roman', serif;
}
```

# Font Weight

This property controls how bold or thin the text appears. It can be specified with keywords or numerical values.


## Keyword Values

The font-weight property can take any one of these keyword values:

* bold: Bold font weight.
* normal: Normal font weight. This is the default value.
* lighter: One font weight lighter than the element’s parent value.
* bolder: One font weight bolder than the element’s parent value

## Numerical Values

Numerical values can range from 1 (lightest) to 1000 (boldest), but it is common practice to use increments of 100. 
A font weight of 400 is equal to the keyword value normal, and a font weight of 700 is equal to bold.

Example:
```CSS
.left-section {
  font-weight: 700;
}

.right-section {
  font-weight: bold; 
}
```
In this example both will appear as bold since the numerical value has exactly the same thickness as the keyword bold.

It’s important to note that not all fonts can be assigned a numeric font weight, and not all numeric font weights are available to all fonts. It’s a good practice to look up the font you are using to see which font-weight values are available.

# Font Style

If we want to italicize text we can do it with this property.
```CSS
h3 {
  font-style: italic;
}
```
Other accepted values are:

* normal - The browser displays a normal font style. This is default	
* oblique - The browser displays an oblique font style	
* initial - Sets this property to its default value.
* inherit - Inherits this property from its parent element. 

# Text Transformation

We can also style text to be either UPPERCASE or lowercase.
```CSS
h1 {
  text-transform: uppercase;
}
```

# Text Layout

## Letter Spacing

This property sets the horizontal spacing between the individual characters in an an element. Uncommon to use but sometimes improves readability. It takes length values in units such as 2px or 0.5em.

```CSS
p {
  letter-spacing: 2px;
}
```

## Word Spacing

This sets the space between idividual words. Again uncommon to use but could enhance readability. Also takes length values.

```CSS
h1 {
  word-spacing: 0.3em;
}
```

## Line Height

Sets how tall each line of text is. Takes unitless number values.
```CSS
p {
  line-height: 1.4;
}
```

## Text Alignment
Aligns text to its parent element.
```CSS
h1 {
  text-align: right;
}
```

# Web Fonts

These are fonts found on the web from free font services such as <a href="https://fonts.google.com/"> Google Fonts</a> or Adobe Fonts. They host the fonts and we can just link to them in HTML with the ```<link>``` element.

We can also use fonts that are downloaded and placed with the site's files. We can then use ```@font-face``` in the CSS stylesheet to link to the relative path of the font files.

## Web Fonts using <link>

Getting a web font from Google Fonts is as simple as browsing the collection then getting the embed for the selected font and style. Google generates the relevant link elements.

```HTML
<head>
  <!-- Add the link element for Google Fonts along with other metadata -->
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@100&display=swap" rel="stylesheet">
</head>
```

Then we can create font-family declarations in CSS.


## Web fonts with @font-face

Fonts come in a few different file formats, such as:

* OTF (OpenType Font)
* TTF (TrueType Font)
* WOFF (Web Open Font Format)
* WOFF2 (Web Open Font Format 2)

These formats are a progression of standards for how fonts will work with different browsers, with WOFF2 being the most progressive. It’s a good idea to include TTF, WOFF, and WOFF2 formats with your @font-face rule to ensure compatibility on all browsers.

Once we have the font files needed we can place them in a folder inside the website's working directory and then use them in the font-face ruleset. 

Example:
``` CSS
@font-face {
  font-family: 'MyParagraphFont';
  src: url('fonts/Roboto.woff2') format('woff2'),
       url('fonts/Roboto.woff') format('woff'),
       url('fonts/Roboto.ttf') format('truetype');
}
```

The *@font-face* is used as the selector. It’s recommended to define it at the top of the CSS stylesheet.
Inside the declaration block, the *font-family* property is used to set a custom name for the downloaded font.
The *src* property contains three values, each specifying the relative path to the font file and its format.

Ordering for the different formats is important because the browser will start from the top of the list and search until it finds a font format that it supports. 
<a href="https://css-tricks.com/snippets/css/using-font-face-in-css/"> More on format prioritization</a>

Once the font-face rule is defined we use the font as normal.
```CSS
p {
  font-family: 'MyLocalFont', sans-serif;
}
```





















