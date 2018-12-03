---
title: Lesson 10
lesson: React State
template: article.jade
lessonId: 10
order: 2

---

Javascript is very good at keeping track of variables and this can be use to keep track of the "state" of something.

State is nothing more than a variable that you want to keep tack of and change from time to time.

React is great at dealing with state.

Lets open `App.js`

```javascript
import React, { Component } from 'react';

class App extends Component {
  render() {
    return (
      <div className="App">
        <h1>No State Here</h1>
      </div>
    );
  }
}

export default App;
```

State can only be added to a javascript class.

I removed some of the unneeded parts of the page.

We need to add a state variable

```javascript
import React, { Component } from 'react';

class App extends Component {
  render() {
    return (
      <div className="App">
        <h1>No State Here</h1>
      </div>
    );
  }
}

export default App;
```

lets add some state

```javascript
import React, { Component } from 'react';

class App extends Component {
  constructor(props) {
    super(props);
    this.state = { clicks: 0 };
  }
  render() {
    ...
  }
}

export default App;
```

Here we added state that counts the the number of times a element has been clicked.

```javascript
class App extends Component {
  constructor(props) {
    super(props);
    this.state = { clicks: 0 };
  }
  render() {
    <div className="App">
      <h1>Total number of clicks - {this.state.clicks}</h1>
    </div>
  }
}
```

Now we need to add a function to update the state let call it `updateClicks()` and it will call `setState` which is build in to react.

```javascript
  updateClicks() {
    this.setState({
      clicks: this.state.clicks + 1
    });
  }
```

`setState` takes a object with the state.  Here we pass in `clicks` with `this.state.clicks + 1`.  This will pull the current state and add one to it.

Now we need to add an `onClick` to call this function

```javascript
<h1 onClick={this.updateClicks}>Total number of clicks - {this.state.clicks}</h1>
```

Here we add on `onclick` and call the `updateClicks` function that we created.

But there we will get an error.

`TypeError: Cannot read property 'setState' of undefined`

`updateClick` does not know what `this` so we need to bind it.

```javascript
  constructor(props) {
    super(props);
    this.state = { clicks: 0 };
    this.updateClicks = this.updateClicks.bind(this);
  }
```

Now if you click the `h1` the number of clicks will grow.

## Final

```javascript
import React, { Component } from 'react';

class App extends Component {
  constructor(props) {
    super(props);
    this.state = { clicks: 0 };
    this.updateClicks = this.updateClicks.bind(this);
  }
  updateClicks() {
    this.setState({
      clicks: this.state.clicks + 1
    });
  }
  render() {
    return (
      <div className="App">
        <h1 onClick={this.updateClicks}>Total number of clicks - {this.state.clicks}</h1>
      </div>
    );
  }
}

export default App;
```