---
title: Lesson 7
lesson: Create DOM Elements
template: article.jade
lessonId: 7
order: 3
---

Up to this point we have been able to make small changes to the the text content but have not been able create new HTML elements.

## createElement()

In javascript if you want to create a element you need to use `createElement()` and pass the element you want in as a variable.

```javascript
var newDiv = document.createElement('div');
```

At this point all we have done create the element but is has no content or is on placed on the page.

## createTextNode()

Since HTML and text are not the same we need to create the test node by using `createTextNode()` and pass in the text we want in.

```javascript
var newDiv = document.createElement('div');
var newContent = document.createTextNode('Created Element');
newDiv.appendChild(newContent);
```

Now we have just added the text to the element but have not written it to the document.

## appendChild()

Just like we added the text to the element by using `appendChild()` we can add the element to the page by using it as well

```javascript
var newDiv = document.createElement('div');
var newContent = document.createTextNode('Created Element');
newDiv.appendChild(newContent);

var body = document.querySelector('body');
body.appendChild(newDiv);
```

This will insert the new `div` at the very end of the body.

## adding attributes

We can add an attribute to the elements that we create by using `setAttribute()`  it takes two properties

The first value is the name of the attribute you want to add.
The next is the value you want to set it to.

```javascript
var newDiv = document.createElement('div');
newDiv.setAttribute('id', 'newId");
var newContent = document.createTextNode('Created Element');
newDiv.appendChild(newContent);

var body = document.querySelector('body');
body.appendChild(newDiv);
```

## adding styles

If we need to add a style to the element created we can use `style`.

```javascript
var newDiv = document.createElement('div');
newDiv.setAttribute('id', 'newId');
newDiv.styles.color = "red";
newDiv.styles.backgroundColor = "black";
var newContent = document.createTextNode('Created Element');
newDiv.appendChild(newContent);

var body = document.querySelector('body');
body.appendChild(newDiv);
```