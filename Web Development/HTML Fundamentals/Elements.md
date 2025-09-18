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

