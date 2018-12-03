---
title: Lesson 10
lesson: Component Lifecycle
template: article.jade
lessonId: 10
order: 3
---

React has some built in lifecycle methods that allow for things to happen at different points on the components life.

### Mounting
These methods are called in the following order when an instance of a component is being created and inserted into the DOM:

* `constructor()`
* static `getDerivedStateFromProps()`
* `render()`
* `componentDidMount()`

### Updating
An update can be caused by changes to props or state. These methods are called in the following order when a component is being re-rendered:

* static `getDerivedStateFromProps()`
* `shouldComponentUpdate()`
* `render()`
* `getSnapshotBeforeUpdate()`
* `componentDidUpdate()`

## Uses

So were would me make the `fetch` call?  `componentDidMount()` is the place were we would put the call.

If we use a lifecycle method we have to use a class component

```javascript
import React, { Component } from 'react';

class Example extends Component {

  componentWillMount() {
    console.log('Did Mount')
  }

  render() {
    return (
      <div>
        <h1>Title</h1>
      </div>
    );
  }
}

export default Example;
```

## Adding fetch

```javascript
import React, { Component } from 'react';

class Example extends Component {
  constructor(props) {
    this.state = {
      data: []
    }
  }
  componentWillMount() {
    fetch('url.com')
      .then(raw => raw.json())
      .then(data => {
        this.setState({data});
      })
  }

  render() {
    return (
      <div>
        <h1>Title</h1>
        {this.state.data.map(item => (<p>item.title</p>))}
      </div>
    );
  }
}

export default Example;
```