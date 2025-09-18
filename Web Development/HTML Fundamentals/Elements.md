# HTML Anatomy

HTML is composed of *elements*. These are organizerd as a collection of family tree relationships. When an element is contained inside another it is considered the c*child* of the *parent* element. We call this nesting and can be infinite.
Most elements have 3 components:
- opening tag
- the content
- closing tag

```HTML
  <div>
    <h1>Sibling to p, but also grandchild of body</h1>
    <p>Sibling to h1, but also grandchild of body</p>
  </div>
```
Child elements can also inherit behavior and styling from their parent.

## The Body
```HTML
    <body> </body> 
```
This is an essential element.
Only the content inside the body tags will be displayed to the user.

## Headings

Headings are headings. Basically titles.
There are 6 sizes starting with ```<h1>``` being the largest (mostly used for main headings) and ```<h6>``` the smallest.

## Divs

Short for "division" the div is a type of container that's used to divide the page into sections. These are useful for grouping elements together.

Particularly useful for styling multiple elements and divs can also be styled themselves as a whole.

## Attributes

These can be added to the opening tag to change the behaviuor or add information. Attributes are made up of two parts: name=value.
A very common attribute is "id" which can be used to specify different content.

## Displaying Text

We can use Paragraphs ```<p>``` or ```<span>``` to show text.

The ```<p>``` is a block element that displays text and styling it will style the whole paragraph. If we want to style only a specific part of the paragraph we can add ```<span>``` to separate it while keeping it in-line. ```<span>``` does not have default properties.

## Styling Text

Text can also be styled with HTML although it's not recommended as it makes it more difficult to make changes.

```<i></i>``` - *Italic* text
```<strong></strong>``` - **Bold** text
etc.
These are pretty much obsolete. Don't use them!

# Line Breaks

Spacing in the code doesn't affect how the content is shown to the user. To insert a new like that is visible we use ```<br>```. No closing tag.

## Unordered Lists

The ```<ul></ul>``` does **not** hold raw text. Instead we need to add individual items with ```<li></li>```
These will appear as a bullet point list.

## Ordered Lists
```<ol></ol>```
Similarly we still need the ```<li>``` for this. Output is a numbered list.

## Images
The ```<img>``` element does **not** have a closing tag. The default attribute for it is *src* which is required to specify the path to the image. This can be an external url.
The *alt* attribute is useful to describe the image both for assistive tech and for SEO purposes.

## Videos
```<video></video>```
This one **DOES** need a closing tag for some reason. Works the same way with *src* but we can also add *width*, *height* and *controls* which are self-explanatory.
We can also add raw text between the tags which will show up if the video is not supported on the browser.

