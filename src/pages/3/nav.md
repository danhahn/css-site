---
title: Lesson 3
lesson: Flex Navigation
template: article.jade
lessonId: 3
order: 5

---

## Building a Navigation

We can use flex box to build a navigation.  In the past this would be complicated but with flex box it takes just one line of code.  But flex box can do so much more.

<iframe height='265' scrolling='no' title='Basic Nav' src='//codepen.io/danhahn/embed/ePYQKB/?height=265&theme-id=light&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/danhahn/pen/ePYQKB/'>Basic Nav</a> by Dan Hahn (<a href='https://codepen.io/danhahn'>@danhahn</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

### html

```html
<nav class="nav-wrapper">
  <ul class="nav-content">
    <li><a href="/">Home</a></li>
    <li><a href="/about">About</a></li>
    <li><a href="/news">News</a></li>
    <li><a href="/weather">Weather</a></li>
    <li><a href="/sports">Sports</a></li>
  </ul>
</nav>
```

### css

```css
.nav-wrapper {
  border: 1px solid black;
  background-color: #c0c0c0;
}

.nav-content {
  display: flex;
}

.nav-content a {
  display: block;
  padding: 1em;
  text-decoration: none;
}

.nav-content a:hover {
  background-color: #0c0c0c;
}
```

## Doing More

Flex box allows us to much more with the nav.

<iframe height='265' scrolling='no' title='Basic Nav -doing more' src='//codepen.io/danhahn/embed/BqaGPg/?height=265&theme-id=light&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/danhahn/pen/BqaGPg/'>Basic Nav -doing more</a> by Dan Hahn (<a href='https://codepen.io/danhahn'>@danhahn</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

The HTML is the same but we added a few properties.

```css
.nav-content li {
  flex: 1;
}
.nav-content a {
  text-align: center;
}
```

