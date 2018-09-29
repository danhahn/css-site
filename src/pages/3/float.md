---
title: Lesson 3
lesson: Float
author: Dan Hahn
date: 2/7/2018 15:00
template: article.jade
lessonId: 3
order: 3
---

## Understanding Float

The float CSS property specifies that an element should be placed along the left or right side of its container, allowing text and inline elements to wrap around it. The element is removed from the normal flow of the web page, though still remaining a part of the flow.

## float

The float property is used for positioning and layout on web pages.

The float property can have one of the following values:

Property | Value
---|---
`left` | The element floats to the left of its container
`right` | The element floats to the right of its container
`none` | The element does not float (will be displayed just where it occurs in the text). **This is default**
`inherit` | The element inherits the float value of its parent

## clear
The clear property specifies what elements can float beside the cleared element and on which side.

Property | Value
---|---
`none` | Allows floating elements on both sides. This is default
`left` | No floating elements allowed on the left side
`right` | No floating elements allowed on the right side
`both` | No floating elements allowed on either the left or the right side
`inherit` | The element inherits the clear value of its parent

The most common way to use the clear property is after you have used a float property on an element.

When clearing floats, you should match the clear to the float: If an element is floated to the left, then you should clear to the left. Your floated element will continue to float, but the cleared element will appear below it on the web page.

The following example clears the float to the left. Means that no floating elements are allowed on the left side (of the div):

<iframe height='465' scrolling='no' title='Floats Explained' src='//codepen.io/danhahn/embed/NgyEJG/?height=265&theme-id=light&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/danhahn/pen/NgyEJG/'>Floats Explained</a> by Dan Hahn (<a href='https://codepen.io/danhahn'>@danhahn</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

## Old Float Layouts

Before more modern CSS layout technique like flex box or grid people would use `float` to create page layouts.

<iframe height='600' scrolling='no' title='Float Homework' src='//codepen.io/danhahn/embed/qPPoEV/?height=265&theme-id=light&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/danhahn/pen/qPPoEV/'>Float Homework</a> by Dan Hahn (<a href='https://codepen.io/danhahn'>@danhahn</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

While it work it is not very flexable.