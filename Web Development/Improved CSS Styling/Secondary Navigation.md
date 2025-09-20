# Breadcrumbs

Secondary navigation, or breadcrumb navigation, usually consists of a clickable list of pages or attributes that led to the current page. It can help users understand the extent of the site and also where they are currently.

We create breadcrumbs with unordered lists in html.

We can add ">" or "/" as a separator for the breadcrumbs directly in CSS by using the *content* property and the "+" (sibling combinator).

For example:

```CSS
.breadcrumb li+li::before {
	padding: 10px;
  content: ">";
}
```

## Breadcrumb Types

There are three major types of breadcrumbs:

* Location
Based on where you are with respect to the navigation structure of the website.

* Attribute
Based on the attributes of the page or product that you are browsing.

* Path
Based on a user’s unique path through the site.

## Breadcrumb Pitfalls

Sometimes it is not appropriate to use breadcrumbs as a means of secondary navigation within a website. Users expect breadcrumbs to behave a certain way and attempts to deviate from this may confuse them. Most users are expecting breadcrumbs to expose the hierarchy of the site or display attributes of the page they are on.

