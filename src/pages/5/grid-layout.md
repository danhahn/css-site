---
title: Lesson 5
lesson: Grid Layout
lessonId: 5
order: 3
---

Like flex box we can use grid to create a layout.  But unlike flex box we have total control over how the page should layout.

### Getting started

```html
<main class="grid-layout">
  <header>header</header>
  <nav>Navigation</nav>
  <article>Content</article>
  <aside>SideBar</aside>
  <footer>footer</footer>
</main>
```

Here we have a simple page layout.  Now we need to add the grid to it.  Like flexbox a grid is a parent to direct child relationship.

Se will be putting the grid on the `main` tag and it will only effect the direct children.

```css
.grid-layout {
  display: grid;
}
```

But at this point it just creates the grid and the default for a grid is a column unlike flex box which is a row.

Next we need to set up our grid.  A grid has both rows and columns and we can set up each.

```css
.grid-layout {
  grid-template-columns: 600px 200px;
  grid-template-rows: 200px 100px 600px 75px;
}
```

The `grid-template-columns` sets up the columns and we will have a column of `600px` and one of `200px`.  At this point the columns are not responsive.

Next we use `grid-template-rows` set up the rows in this case we have 4 rows.

We now how a grid with 4 rows and 2 columns.  Each child element will auto full the grid based on the order they are defined in the html and will take up one "cell" in the grid.

### Placing the Content

Now that we have our grid set up we need to place the content on the gird.  As noted before the content will auto fill the grid based on the order it is defined in the html and will only take on "cell" in the grid.  It also should be noted that the grid takes up the space defined in the the steps above even though there no content in it.

`grid-column` and `grid-row` are used to define how the grid is layed out.

With grid we dont count the rows or columns but the space between the them.  This is numbered base on the number of items.  In our case we have two columns so we will have three gaps.  The space before the first column the space between the columns and the space after the last column.  They are numbered 1, 2 and 3 but if more columns are added they will renumber and add more based on the number of columns.  There will always be one more gap than column or row.  Since you may not know the number of columns or row there is a handy alterative to get the last "gap" by defining `-1`.

Let make the header span the full width of the grid

```css
header {
  grid-column-start: 1;
  grid-column-end: 3;
}
```

There is a shorthand for this of `grid-column` and we define the start and end in a single property but the values need to be seperated by a `/`.

```css
nav {
  grid-column: 1 / 3;
}
footer {
  grid-column: 1 / 3;
}
```

This will align the page the way we want because the `article` and `aside` just "flow" to the correct locations.

But if we needed to define there location we could by doing this

```css
article {
  grid-column: 1 / 2;
}

aside {
  grid-column: 2 / 3;
}
```

Notice that both have defined `2` that is because we ending and starting that the same gap.