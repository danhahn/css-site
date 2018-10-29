---
title: Lesson 5
lesson: Adv Grid
lessonId: 5
order: 4
---

There are number of more advanced this that will make grid more flexible.

## repeat

When you start to build ou more complex grids we will need to add more columns.

```css
main {
  display: grid;
  grid-template-columns: 100px 100px 100px 100px 100px 100px;
}
```

This will create a grid of 6 columns of 100px.

But we could use the `repeat()` method to make the a bit easy to work with.

```css
main {
  grid-template-columns: repeat(6, 100px);
}
```

This will produce the same layout as the above example but a little easier to work with.

You can use the `repeat()` in the middle of standard values.

```css
main {
  grid-template-columns: 200px repeat(6, 100px) 75px 80px;
}
```

## auto

sometimes you may want to set a row or column but want the content to set the size.  In this case you will need to use `auto`

```css
main {
  grid-template-columns: 200px repeat(6, 100px) auto;
}
```

**Note:** This will work the same for both `grid-template-columns` and `grid-template-rows`.

## fr unit

The `fr` unit stands for fractal remains in other words now should the grid deal with any extra space with in the grid. Like `flex-grow` but a little more straightforward.

lets saw we want to create a 4 column layout.  We could do this.

```css
main {
  grid-template-columns: repeat(4, 100px);
}
```

This will take only 400px and there may be extra space that we want to give to each column.  This is where the `fr` unit comes in.

`1fr` will be one unit of the remainder of space.

So lets say we have 1000px of space to work with and our grid has 4 columns of 100px.  We have 600px of space extra that is divided by the number of columns (600 / 4 = 150) and each column would get an extra 150px.  But unlike flex box were we have a base width here we just divide the exrta space by the number of columns and give each "columm" one unit.

`1000 / 4 = 250px`  so in this example `1fr` === 250px;

We would write the css like this

```css
main {
  grid-template-columns: repeat(4, 1fr);
}
```

## minmax

There are times where you will want to set a value that can adjust between two values.  Helps make the page more responsive.

```css
main {
  grid-template-columns: 100px minmax(300px, 500px) 200px;
}
```

Here we have a column that is 100px, any width between 300px and 500px, then 200px;  The second column will adjust based on the space it has.

We can replace the second value with an `fr`.

This can be very handy when you want make columns that are able to adjust to a space and by using `repeat` it can be one in one line.

```css
main {
  grid-template-columns: repeat(4, minmax(200px, 1fr));
}
```

This will create 4 columns that are at least 200px and at max the full with divided by 4.

## autofix

`autofix` allows the grid to choose the number of columns based on the space.

```css
main {
  grid-template-columns: repeat(autofix, 100px));
}
```

Here we will have as many 100px columns that will fix in the space.

This will leave a little space at the end since you might have a browser width of 780 and that will only allow for 7 100px columns so we would have an extra 80 of space.

We can use `minmax` to fix this.

```css
main {
  grid-template-columns: repeat(autofix, minmax(100px, 1fr)));
}
```

So now the extra 80px will be divided by 7 and the remain given to each column.