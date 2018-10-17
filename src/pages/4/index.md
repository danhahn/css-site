---
title: Lesson 4
index: true
lesson: Flex Layouts
template: article.jade
lessonId: 4
order: 1

labels: [Download Stater File]
attachments:
  - "./week4.zip"

badges: [css]
---

This week we will be talking about how to use flex box to build a page layout and make it responsive.

<span class="more"></span>

Flex box is great at creating smaller components like a nav or promo area but we can use flex box to create a full page layout as well.  Since flex box is designed to be flexible it great for creating responsive layouts.

Before we can get to the responsive parts we need to understand how to create a basic layout. Our goal is to create two layouts one a two column layout and one a three column layout.  The basic ideas are the same for each.

<iframe height='500' scrolling='no' title='flex box layout example 2018' src='//codepen.io/danhahn/embed/ZqpbZR/?height=265&theme-id=light&default-tab=result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/danhahn/pen/ZqpbZR/'>flex box layout example 2018</a> by Dan Hahn (<a href='https://codepen.io/danhahn'>@danhahn</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

Let looks at what the basic page layout might look like.

```html
<main>
  <header></header>
  <nav></nav>
  <article></article>
  <footer></footer>
</main>
```

This will create a simple on column layout where with each "section" stacked on top of each other.  Something like this will work well for screens that are not too wide but as we increase the width we have more flexibility in how we can layout the page.

We want to have the same "sections" of the page but we want to lay them out so the `header` is stacked on top of the `nav` and `article`.  To do this we need to create a "row".  In this case a "row" is nothing more than a wrapper that we can use to flex our content.

Let look at the updated html.

```html
<main>
  <header></header>
  <section>
    <nav></nav>
    <article></article>
  </section>
  <footer></footer>
</main>
```

Here we added a `section` tag but could have been any block element. The `section` will be our "row" and where we set the flex box.

```css
section {
  display: flex;
}
```

This will create a simple flex row.   But the content in the "row" is not alined the way we want.  Lets assume that we want the `nav` to be `200px` wide and the `article` should get the rest of the space.


```css
section {
  display: flex;
}

nav {
  flex: 0 0 200px;
}

article {
  flex: 1;
}
```

This will se the `flex` on the `nav` to not grow, no shrink and have `flex-basis` of 200px.  For the `article` we said take the remainder of the space and give it to the article.

### Make a three column

Going to from a two column to a three column is easy.  We just need to update the html to have an other "section" in this case an `aside`.

```html
<main>
  <header></header>
  <section>
    <nav></nav>
    <article></article>
    <aside></aside>
  </section>
  <footer></footer>
</main>
```

Likewise we need to update the CSS to deal with this new "section".

```css
section {
  display: flex;
}

nav {
  flex: 0 0 200px;
}

article {
  flex: 1;
}

aside {
  flex: 0 0 300px;
}
```

This will create a three column layout the the first and third columns taking up 500 total pixels.  So we need to ensure there enough for the content to be displayed so this width should be greater than 1000px.   But what happens if our screen with is less than 1000px?  That is where we can use flex with [media queries](media.html) to change the CSS based on the screen with.