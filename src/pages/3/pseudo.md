---
title: Lesson 3
lesson: Pseudo
author: Dan Hahn
date: 2/7/2018 15:00
template: article.jade
lessonId: 3
order: 2

tags:
---

Pseudo class will apply a style when a "case" is true.  The most common pseudo classes are related to the state of a link.

Here we have a simple link.  Notice that three are no classes names on it.

```html
<a href="http://www.google.com">Just a link</a>
```

By using a pseudo class we can style the link when any of the cases are met.

* The first selector will target all `a` tags regardless of any other state.
* `:link` will style the link when the url in not in the browser history
* `:visited` will style when the link when the link in the browser history
* `:hover` will style when the mouse is over the link
* `:active` will style the link when the user is clicking the link.

```css
a {
  color: red;
  text-decoration: none;
}
a:link {
  color: orange;
}
a:visited {
  color: green;
}
a:hover {
  color: pink;
  text-decoration: underline;
}
a:active {
  color: yellow;
}
```

An element can be in more than one state at once.  Here when the user is clicking the link the valid states would be `:link`, `:hover` and `:active`.  All pseudo selectors do not change the weight of the selector in that case the selectors all carry the same weight and wall fall back to the order defined in the css file.  This is why we place `:active` last otherwise we would not see the active color because `:hover` would be displayed.

## `:hover`
It is valid to place a `:hover` on any html element.

```html
<header class="global-header">
  <h1>Page Header Text</h1>
</header>
```

When a user move their mouse over the `.global-header` element the background will change color.

```css
.global-header {
  background-color: blue;
}
.global-header:hover {
  background-color: red;
}
```

## pseudo class

Selector | Example | Example description
---|---|---
`:active` | `a:active` | Selects the active link
`:checked` | `input:checked` | Selects every checked `<input>` element
`:disabled` | `input:disabled` | Selects every disabled `<input>` element
`:empty` | `p:empty` | Selects every `<p>` element that has no children
`:enabled` | `input:enabled` | Selects every enabled `<input>` element
`:first-child` | `p:first-child` | Selects every `<p>` elements that is the first child of its parent
`:first-of-type` | `p:first-of-type` | Selects every `<p>` element that is the first `<p>` element of its parent
`:focus` | `input:focus` | Selects the `<input>` element that has focus
`:hover` | `a:hover` | Selects links on mouse over
`:in-range` | `input:in-range` | Selects `<input>` elements with a value within a specified range
`:invalid` | `input:invalid` | Selects all `<input>` elements with an invalid value
`:lang(language)` | `p:lang(it)` | Selects every `<p>` element with a lang attribute value starting with "it"
`:last-child` | `p:last-child` | Selects every `<p>` elements that is the last child of its parent
`:last-of-type` | `p:last-of-type` | Selects every `<p>` element that is the last `<p>` element of its parent
`:link` | `a:link` | Selects all unvisited links
`:not(selector)` | `:not(p)` | Selects every element that is not a `<p>` element
`:nth-child(n)` | `p:nth-child(2)` | Selects every `<p>` element that is the second child of its parent
`:nth-last-child(n)` | `p:nth-last-child(2)` | Selects every `<p>` element that is the second child of its parent, counting from the last child
`:nth-last-of-type(n)` | `p:nth-last-of-type(2)` | Selects every `<p>` element that is the second `<p>` element of its parent, counting from the last child
`:nth-of-type(n)` | `p:nth-of-type(2)` | Selects every `<p>` element that is the second `<p>` element of its parent
`:only-of-type` | `p:only-of-type` | Selects every `<p>` element that is the only `<p>` element of its parent
`:only-child` | `p:only-child` | Selects every `<p>` element that is the only child of its parent
`:optional` | `input:optional` | Selects `<input>` elements with no "required" attribute
`:out-of-range` | `input:out-of-range` | Selects `<input>` elements with a value outside a specified range
`:read-only` | `input:read-only` | Selects `<input>` elements with a "readonly" attribute specified
`:read-write` | `input:read-write` | Selects `<input>` elements with no "readonly" attribute
`:required` | `input:required` | Selects `<input>` elements with a "required" attribute specified
`:root` | `root` | Selects the document's root element
`:target` | `#news:target` | Selects the current active #news element (clicked on a URL containing that anchor name)
`:valid` | `input:valid` | Selects all `<input>` elements with a valid value
`:visited` | `a:visited` | Selects all visited links

##All CSS Pseudo Elements

Pseudo elements are style that will change the html structure of a page.  ``::after`` will inject a inline element after the text of the element. It will only display when the `content` property is defined in the css.

```css
h3::after {
  content: "⭐";
}
```

**Note:** Pseudo element are not part of the page structure and can not be selected or copied by the user.  The content in a pseudo element will not affect your search engine optimization (SEO).

### After Example

Selector | Example | Example description
---|---|---
`::after` | `p::after `| Insert content after every `<p>` element
`::before` | `p::before` | Insert content before every `<p>` element
`::first-letter` | `p::first-letter` | Selects the first letter of every `<p>` element
`::first-line` | `p::first-line` | Selects the first line of every `<p>` element
`::selection` | `p::selection` | Selects the portion of an element that is selected by a user

<style>
:not(pre) > code[class*="language-"] {
  white-space: nowrap;
}
h3::after {
  content: "⭐";
}
</style>