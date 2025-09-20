By default, browsers include a user agent stylesheet, a set of default styles included with the browser (“user agent”) for use on all web pages. 
While designers often overwrite these, it’s important to maintain a consistent user experience pattern, like the default behavior applied by browsers.

Traditionally, links are differentiated from regular text using blue text and underlines to draw users’ attention to their clickability. Many websites and user agent stylesheets still use these link styles.

Browsers also style two other link states: clicked (‘active’), and previously visited. In most user agent stylesheets, clicked (but not yet followed) links appear with red text, and previously visited links are styled with purple text.

# Link Styling

Link styles should not be replicated in other page text. Link color should sufficiently contrast the text colors in the rest of the design.

# Tooltips and Titles

The *title* attribute in HTML is especially useful for providing additional context to an element, and most browsers will display it as a tooltip when the user hovers over the element.
However, it is known to cause a <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Global_attributes/title#accessibility_concerns"> lot of accessibility issues </a> so it's generally not recommended to use it. Instead we can use CSS and JS.

# Hover States and Cursors

The CSS pseudo-class *:hover* can be used to style elements on mouse hover. For example, changing a link color on mouse hover.

Usage example:
```CSS
a {
  color: blue;
}

a:hover {
  color: orange;
}
```

We can also make the cursor change to a pointing hand by using the *cursor* property. Example:
```CSS
a {
  cursor: pointer;
}
```
This is usually included in the default browser behavior but we can use it for customization.

# Link States

Links have four main states: normal (not clicked), hover, active (clicked), and visited. 
These four states have associated CSS pseudo-classes: :link, :hover, :active, and :visited.

We can use these to give a full range of visual feedback to the user.

The ordering of these is important. The proper order is:

* :link
* :visited
* :hover
* :active

This ensures that the rules <a href="https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Handling_conflicts"> cascade properly </a>.

# Skeuomorphism and Flat Design

The concept of UI elements that replicate or imitate real-life counterparts is known as skeuomorphism. They have an old-school 3D effect.

Flat is flat. It's just a box with rounded corners and text.

The <button> element comes with default styles that give it the button look - *border* and *background-color*.

## Buttons: Skeuomorphic styling

This design aims to imitate the appearance of a real-life button, often including a ‘raised’ appearance while the button is unpressed and a ‘pressed’ appearance when clicked.

This can be implemented using images and css rules, however designing solely with CSS is preferred as it loads faster and modern CSS3 has support for 2D and 3D effects.

Basic 3D button example with CSS only:

```CSS
button {
  padding: 5px;
  border: 1px solid black;
  border-radius: 5px;
  text-decoration: none;
  box-shadow: 0px 5px;
}

button:hover {
  cursor: pointer;
}

button:active {
  margin-top: 5px;
  color: black;
  box-shadow: 0px 0px;
}
```

## Buttons: Flat Design

Flat design buttons commonly appear as rectangles, rounded rectangles, or circles. These shapes are used ubiquitously for button elements, so users often perceive them as buttons and expect them to be clickable.

To make these we just create a *border* and add a *background-color*.

## Buttons: Hover States

Just as with links, buttons should make use of hover states and the cursor: pointer declaration. 
