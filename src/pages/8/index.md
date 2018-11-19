---
title: Lesson 8
index: true
lesson: Intro to ReactJs
template: article.jade
lessonId: 8
order: 1

labels: [Download Stater File]
attachments:
  - "./week8.zip"

badges: [html, javascript]
---

This week we start to talk about ReactJS and how we can use it to build a Single Page App.

<span class="more"></span>

ReactJs is build by the team at Facebook to solve one of the big problems of a web application in that when you update a part of the page the whole page needed to render again.

When we use any of the standard JavaScript methods to update part of a page the whole page needed to be rendered again.  This is slow and can be problematic.  React introduces the virtual dom where the DOM elements are lightweight copies of the DOM but lack the power to change the real thing.  React will do all the updates and is able to update on the element that changes and does not requirer a full page render.

## Getting started

In the last lesson we learned how we can create an element via JavasScript.

<iframe height='265' scrolling='no' title='create element' src='//codepen.io/danhahn/embed/KrWYNR/?height=265&theme-id=light&default-tab=js,result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/danhahn/pen/KrWYNR/'>create element</a> by Dan Hahn (<a href='https://codepen.io/danhahn'>@danhahn</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

Here we did it the old school way and added a new div to the page.

## Change to React

Since React is a library that sits on top of JavaScript we need to add it to our pages.

```html
<script src="https://unpkg.com/react@16.3.1/umd/react.production.min.js"></script>
<script src="https://unpkg.com/react-dom@16.3.1/umd/react-dom.production.min.js"></script>
<script type="text/javascript">

</script>
```

Once we do that we need to use the react API to create an element.  It is a lot like JavaScript but is able to set everything at once.

<iframe height='265' scrolling='no' title='react create element' src='//codepen.io/danhahn/embed/XyMQVw/?height=265&theme-id=light&default-tab=js,result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/danhahn/pen/XyMQVw/'>react create element</a> by Dan Hahn (<a href='https://codepen.io/danhahn'>@danhahn</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

`React.createElement()` takes three things.

1. The type of element
2. any attributes
3. the content

## Adding JSX

We could write our full app using `createElement()` but it would not be easy or fun.  As an alterative we can use **JSX** or JavaScript and XML.  It allows you to write HTML like code in your JavaScript that is then converted over to JavaScript and `createElement()`.

JSX is not supported in JS by default.  We need a tool to convert JSX to pure JavaScript to do this we will use Babel.

We need to add the script to your html file and update the script's tag `type` to be `text/babel`

```html
<script src="https://unpkg.com/babel-standalone@6.26.0/babel.js"></script>
<script type="text/babel">

</script>
```

<iframe height='265' scrolling='no' title='react create element JSX' src='//codepen.io/danhahn/embed/KrWLML/?height=265&theme-id=light&default-tab=js,result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/danhahn/pen/KrWLML/'>react create element JSX</a> by Dan Hahn (<a href='https://codepen.io/danhahn'>@danhahn</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

There are a few thing that are different between JSX and JavaScript

* a css class is set in `className` not `class`
* styles are defined as an object
* can set variables in the JSX
* All tags must be closed

### Setting a variable

```javascript
var root = document.getElementById('root');

const content = "hello World!";
const myClassName = "container"

const element = <div class={myClassName}>{content}</div>

ReactDOM.render(element, root);
```

**Note:** when you use `{}` in JSX you are able to write most any JavaScript

### Spreading Props

In JavaScript if you have an object and want to use all the values that object you can spread `...` the out.

Here we create an object and set `className` and `children` then spread them over the `<div />`.

```javascript
var root = document.getElementById('root');

const props = {
  className: "container",
  children: "Hello World!"
}

const element = <div {...props}/>

ReactDOM.render(element, root);
```

**Note:** Since JSX is not HTML but XML and XML requires that all tags are closed we must make sure that all tags are closed.  If a tag is not wrapping anything we can use a self closing tag `<div/>`.

## Creating reuseable components

One of the the things tha makes react so enjoyable is that we are able to create smaller components that can be reused over and over.

Lets say we want to display "Hello World" more than once.  We can create a variable and then use it in the JSX.  Notice that variable is also JSX.

But it not very reuseable we get the same output every time.

```javascript
const rootElement = document.getElementById('root')
const helloWorld = <div>Hello World</div>
const element = (
  <div className="container">
    {helloWorld}
    {helloWorld}
  </div>
)
ReactDOM.render(element, rootElement)
```

Lets refactor things a bit.

We change the variable to an arrow function and pass in an object with the key of `msg` and use that to fill the JSX.

Then we call the function and pass in am object with the value we want to display.

```javascript
const message = props => <div>{props.msg}</div>
const element = (
  <div className="container">
    {message({msg: 'Hello World'})}
    {message({msg: 'Goodbye World'})}
  </div>
)
```

Functions don't read very well.  JSX is much easier to read so let try to convert the `message` to a createElement

```javascript
const message = props => <div>{props.msg}</div>
const element = (
  <div className="container">
    {React.createElement(message, {msg: 'Hello World'})}
    {React.createElement(message, {msg: 'Goodbye World'})}
  </div>
)
```

<iframe height='265' scrolling='no' title='convert to component' src='//codepen.io/danhahn/embed/ZmedZx/?height=265&theme-id=light&default-tab=js,result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/danhahn/pen/ZmedZx/'>convert to component</a> by Dan Hahn (<a href='https://codepen.io/danhahn'>@danhahn</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

again this is not much more readable so let try to use `message` as JSX.

```javascript
const message = props => <div>{props.msg}</div>
const element = (
  <div className="container">
    <message></message>
    {React.createElement(message, {msg: 'Hello World'})}
    {React.createElement(message, {msg: 'Goodbye World'})}
  </div>
)
```

But this will not work.  React needs some way to know what is HTML and what is JSX.  To indicate that something is a component and not HTML it must start with a capital letter.

```javascript
const Message = props => <div>{props.msg}</div>
const element = (
  <div className="container">
    <Message></Message>
    {React.createElement(Message, {msg: 'Hello World'})}
    {React.createElement(Message, {msg: 'Goodbye World'})}
  </div>
)
```

So lets use this.

```javascript
const Message = props => <div>{props.msg}</div>
const element = (
  <div className="container">
    <Message msg='Hello World'/>
    <Message msg='Goodbye World'/>
  </div>
)
```

But remember we can pass our `msg` as a children.

```javascript
const Message = props => <div>{props.children}</div>
const element = (
  <div className="container">
    <Message children='Hello World'/>
    <Message children='Goodbye World'/>
  </div>
)
```

Or even better

```javascript
const Message = props => <div>{props.children}</div>
const element = (
  <div className="container">
    <Message>Hello World'<Message/>
    <Message>Goodbye World'<Message/>
  </div>
)
```

so now we have a component that looks a lot like HTML and is easy to compose