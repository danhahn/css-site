---
title: Lesson 2
lesson: Overflow
author: Dan Hahn
template: article.jade
lessonId: 2
order: 7
---

Definition and Usage
The `overflow` property specifies what should happen if content `overflows` an element's box.

This property specifies whether to clip content or to add scrollbars when an element's content is too big to fit in a specified area.

**Note:** The `overflow` property only works for block elements with a specified height.

Value | Description
---|---
`visible` | The overflow is not clipped. It renders outside the element's box. This is default
`hidden` | The overflow is clipped, and the rest of the content will be invisible
`scroll` | The overflow is clipped, but a scroll-bar is added to see the rest of the content
`auto` | If overflow is clipped, a scroll-bar should be added to see the rest of the content
`initial` | Sets this property to its default value. Read about initial
`inherit` | Inherits this property from its parent element. Read about inherit


### Visible

<iframe height='574' scrolling='no' title='Overflow: Visible ' src='//codepen.io/danhahn/embed/gMmPdE/?height=574&theme-id=light&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/danhahn/pen/gMmPdE/'>Overflow: Visible </a> by Dan Hahn (<a href='https://codepen.io/danhahn'>@danhahn</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

### Hidden

<iframe height='355' scrolling='no' title='Overflow: Hidden' src='//codepen.io/danhahn/embed/rqaYoW/?height=355&theme-id=light&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/danhahn/pen/rqaYoW/'>Overflow: Hidden</a> by Dan Hahn (<a href='https://codepen.io/danhahn'>@danhahn</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

### Scroll

<iframe height='343' scrolling='no' title='Overflow: Scroll' src='//codepen.io/danhahn/embed/PywOXV/?height=343&theme-id=light&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/danhahn/pen/PywOXV/'>Overflow: Scroll</a> by Dan Hahn (<a href='https://codepen.io/danhahn'>@danhahn</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

### Auto

<iframe height='336' scrolling='no' title='Overflow: Auto' src='//codepen.io/danhahn/embed/JmoOxO/?height=336&theme-id=light&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/danhahn/pen/JmoOxO/'>Overflow: Auto</a> by Dan Hahn (<a href='https://codepen.io/danhahn'>@danhahn</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>