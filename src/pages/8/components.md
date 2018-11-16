---
title: Lesson 8
lesson: Create Components
template: article.jade
lessonId: 8
order: 2

---

There are two ways we can create a component in React.  

1. Stateless
2. Statefull

In the last example we created a stateless component.  This is a simple function that is called and we can pass in the props in to the functions.  This function does not have a "state" or access to any of the react life cycle hooks.

## Stateless functional component

A stateless functional component is a function that returns JSX.  It does not have access to create or set "state".  It is a simple function that `return` some JSX or react code.  It will have a name that is used to call the component and must start with a capital letter.  

```javascript
function Box() {
  return (<div></div>)
}
```

We created a function `Box` and this function `returns` the JSX `<div></div>`.

Since we need to the JSX to be interpolated to React code we must wrap it with `()`.  

We can pass props to the function and they will render but we can do this a little more cleanly by `destructuring` the object

```javascript
function Box(props) {
  return (<div>{props.children}</div>)
}
```

### destructuring

```javascript
const props = {
  className: "title",
  isActive: true,
  children: "We Love React"
}

// we need to the value of the object.  One way is to create a variable for each.

var className = props.className;
var isActive = props.isActive
// and so on.  this leads to lots of code that could be done in one line of code.

const {className, isActive, children} = props;
// This dose the same thing as above buy in one line of code.

// if we pass a object to a function we can just destruct it from in the function name.

function Message({className, isActive, children}) {
  return (
    <div className={className} isActive>{children}</div>
  )
}
```

So if we use it we could make this a little more clean.

```javascript
function Box({children}) {
  return (<div>{children}</div>)
}
```
or we could do this as an arrow function 

```javascript
const box = ({children}) => (
  <div>{children}</div>
)
```

## Class Component 

In the event that you want to do more with your react component that just display it you will need to use a `class` component.  

**Note:** This is why we can't define just the a "class" for css class names.

Creating a class is a little more complex.

```javascript
class Box extends React.Component {
  render() {
    return (<div></div>);
  }
}
```

Here we extend the `React.Component` and name it `Box`.  In our class we need to have at least a `render` function that `returns` the JSX.

But what if we pass in props?  We will still deconstuct them the props.  

```javascript
class Box extends React.Component {
  render() {
    const {children} = this.props;
    return (<div>{children}</div>);
  }
}
```

We now have a `this` that just points to the class as hold.  We will use `this` more later on.  

<iframe height='265' scrolling='no' title='React Class' src='//codepen.io/danhahn/embed/QJvWPg/?height=265&theme-id=light&default-tab=js,result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/danhahn/pen/QJvWPg/'>React Class</a> by Dan Hahn (<a href='https://codepen.io/danhahn'>@danhahn</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>