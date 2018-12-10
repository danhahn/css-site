---
title: Lesson 11
lesson: SCSS
template: article.jade
lessonId: 11
order: 2
---

SCSS is css that is run thought a preprocessor.  A preprocessor is a middleware that sits between the `.scss` file and the out `.css`.

There are a number advantages you by using a preprocessor to create your css.

## Variables

```css
$blue: #004BB4;
h1 {
  color: $blue;
}
```

## Nested Syntax

```css
.navbar {
  color: $blue;
  li {
    margin-left: 1rem;
    a {
      padding: 5px;
      font-size: 1.5rem;
      span {
        font-weight: 600;
      }
    }
  }
}
```

## mixins

Let's look at an example. Imagine you have this mixin:
```css
@mixin set-font( $family: 'Ubuntu' , $weight: 400 , $style: normal ) {
  font-family: $family , 'Arial', 'Helvetica', sans-serif;
  font-style: $style;
  font-weight: $weight;
}
```
Now that you have your mixin defined, you can include it wherever you want. Note that because you have declared default values there is no need to pass any parameter:
```css
h1 {
  @include set-font;
  color: $blue;
}
```
This will be compiled into:
```css
h1 {
  font-family: 'Ubuntu', 'Arial', 'Helvetica', sans-serif;
  font-style: normal;
  font-weight: 400;
  color: #004BB4;
}
```

## Setting up SCSS

Since we are using a preprocessor we can not just write scss in our html file we need to use a tool to convert it over to a css file.

### tools

https://sass-lang.com/install has a list of some tools that you can use.

I like to use https://codepen.io/ it is a great place to start to code a page and it allows you to write scss with in the application.

### Adding create react app

We can also add to our react app.

We can use scss in our react app but including a `.scss` file vs a `.css`.

We need to add the `node-sass` package to make it work.

`npm install node-sass --save`

Then include the `scss`

`import ./styles.scss`

