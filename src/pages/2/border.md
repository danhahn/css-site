---
title: Lesson 2
lesson: Border
author: Dan Hahn
date: 09/25/2017 18:00
template: article.jade
lessonId: 2
order: 6

nav:
  Font Properites: index.html
  Text Properties: text.html
  Include File: include.html
  Define a color: color.html
  CSS Units: sizes.html
  Borders: borders.html
  Padding: padding.html
  Margin: margin.html
  Pseudo: pseudo.html
  overflow: overflow.html
  Homework: homework.html
---

Borders can be added to most every element and are made up of three parts.

Value | Description
---|---
`border-width` | Specifies the width of the border. Default value is "medium"
`border-style` | Specifies the style of the border. Default value is "none"
`border-color` | Specifies the color of the border. Default value is the color of the text

A border can’t be defined on an element with out at least the border-style because there is no default value.  If you only define a border-style the border will be 3px thick and have the current font color.

`border-*` will define the border for all sides.  If you need to define a border for only side there are border-[top,right,bottom,left]-[width,style,color] that can be used.

### Short Hand

```css
border: border-width border-style border-color|initial|inherit;
```

### Real world example

```css
border: 10px solid blue;
```

### For example

```css
border-bottom-width: 1px;
border-bottom-style: solid;
border-bottom-color: green;
```

### Using border
CSS has short hand way to easily define a border.  The border property takes up to three values.

```css
border: {width} {style} {color};
```

The only required property is style, the other two are option but recommended.  If the options values are not set the are set to the default value.

Again if you need to target one side of a border you can use border-[top,right,bottom,left].
### For example

```css
border-top: 2px dashed #ff00ff;
```

Since you can only define one value for each option in the shorthand there is no easy way to set each side to a different value.  In this case you will need to set each with its own property.

### For example

```css
border-top: 10px dotted blue;
border-bottom: 8px solid yellow;
```
