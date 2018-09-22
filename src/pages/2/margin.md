---
title: Lesson 2
lesson: Margin
author: Dan Hahn
template: article.jade
lessonId: 2
order: 8
---

Margin is the space from one element `border` to another element `border`. What this means that that you are note setting the space from the edge of margin but the element itself.  Margins can overlap.

Margin will define all four sides of the box one value is set. If you need to define the margin of just one side of the box you can use `margin-[top,right,bottom,left]`.

<iframe height='500' scrolling='no' title='Padding' src='//codepen.io/danhahn/embed/MoQYeQ/?height=265&theme-id=dark&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/danhahn/pen/MoQYeQ/'>Padding</a> by Dan Hahn (<a href='https://codepen.io/danhahn'>@danhahn</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

### Example

```css
margin-top: 20px;
margin-bottom: 20px;
```

Just like padding the number of values you place effects different sides.

```css
margin: (All Sides);
margin: (top and bottom) (left and right);
margin: (top) (left and right) (bottom);
margin: (top) (right) (bottom) (left);
```

## Center Container

The problem with centering `#container` on the page is there is no real property that does this. Your first thought might be `text-align: center;` but that will just center the text within the elements.

By setting the `margin` on the left and right to `auto` the element will be centered on the page. Because we set the left and right to auto it take the space left over after the and divide it by 2 and set it equal to each other. This will make the element center on the page.

```html
<style>
    #container {
        width: 800px;
        margin: 0 auto;
    }
</style>
```
