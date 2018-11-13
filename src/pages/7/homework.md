---
title: Lesson 7
lesson: Homework
template: article.jade
lessonId: 7
order: 5

labels: [Download Stater File]
attachments:
  - "./homework-lesson7.zip"


badges: [javascript]
---

This week will be using JavaScript to hide and show the navigation when the user clicks a button.

## What will we cover in this homework?

* Query the DOM for HTML elements
* Adding event listener 
* toggling classes
* update the text of the button based on the "state"

## Getting Started

* Download the Starter file
* Add a `script` to the document

## Query the DOM

Create a variable and set it to the DOM element for 

* `.clickMe` - btn
* `.global-nav` - nav

## Create a boolean

Create a variable `isHidden` and set to `false`.

## create a function

We need a function to do everything when the button is clicked.  

Create a function `hideNav()`

Within the function you will need to 

1. `toggle` the class `active` on the `btn`
2. `toggle` the class `hide` on the `nav`
3. change the value of `isHidden` to the other state (more on this below)
4. Update the text of the `btn` based on the state of `isHidden`
  * if `isHidden` is true - "Show Nav"
  * otherwise the `btn` - "Hide Nav"

**Note:** if you want to get the opposite value of a boolean you can add the not `!` in front.  So if set `var isHidden = false` and want to set it to true you can just define `isHidden = !isHidden`.

## Add eventListener 

Last we need to add an `eventListener` to `btn` and call the function we created above `hideNav`.  In this case we are going to call the function from the listener and not use the arrow function.

This is an example of what it might look like.

```javascript
element.addEventListener('click', functionName);
```

## Final Product

[code page](https://codepen.io/danhahn/full/rQjdap/)