# DOCUMENT Standards

In order for the browser to know what they're reading we need to add the declaration. That's done with ```<!DOCTYPE html>```.
This **MUST** be the very first line in the file! 

## HTML tag

We also need to add ```<html></html>``` at the start and end of the document.

## HEAD tag
```<head></head>``` contains the metadata like the page title.

## Page Titles
```<title></title>``` - it's the page title. Not much more to say.

## Linking to other pages
```<a></a>```
The anchor element is used to add links to other pages both internal and external. It needs the **href** attribute and can also contain raw text which becomes clickable.
Example: ```<a href="cruncyroll.com"> Crunchyroll </a>```

Linking to another page in the same folder is done with href="./anotherpage.html". If the page is local but not in the same folder then we specify the path to it still starting with ./

This can also be used to link to element IDs on the same page. For example:
```<a href="#contact> Contact </a>```
This will take the user to the element on the same page with the attribute id="contact".

Adding the attribute **target="_blank"** will open the link in a new tab.

## Whitespace and Indentation

Used to make the code more readable (besides nesting elements).

## Comments
```<!-- This is a comment -->`` It's a comment. Use it a lot to help others understand your spaghetti (codebase).

