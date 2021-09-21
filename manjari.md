# Interview Questions for Manjari

## 1 

Given below an array of object with duplicates, each object has an 'id' that can be used to identify it. Remove the duplicate object with lower rank.

```javascript
const gamers = [
    {
        id: 1,
        name: 'Jason',
        rank: 4,
    },
    {
        id: 2,
        name: 'Oxmond',
        rank: 1,
    },
    {
        id: 2,
        name: 'Oxmond',
        rank: 2, 
    },
    {
        id: 3,
        name: 'Authur',
        rank: 3,
    },
]
```

- The duplicate objects cannot be removed using (Set) because the 2 objects has the same structure and their data have different references
- (Map) can be used to have 'id' as the key and object as value
- If 'id' is already present in the array, object with the higher rank can be retained

## 2

### React Toggle Button

We provided some simple React template code. Your goal is to modify the component so that you can properly toggle the button to switch between an ON state and an OFF state. When the button is on and it is clicked, it turns off and the text within it changes from ON to OFF and vice versa. Make use of component state for this challenge.

You are free to add classes and styles, but make sure you leave the element ID's as they are. Submit your code once it is complete and our system will validate your output.

```javascript
import React, { useState } from 'react';
import ReactDOM from 'react-dom';

class Toggle extends React.Component {
  constructor(props) {
    super(props);
  }

  handleClick() {
    // todo
  }

  render() {
    return (
      <button>ON</button>
    );
  }
}

ReactDOM.render(
  <Toggle />,
  document.getElementById('root')
);
```

## 3

Take a look at the code below:

```javascript
class MyComponent extends React.Component {
  constructor(props) {
    // set the default internal state
    this.state = {
      clicks: 0
    };
  }

  componentDidMount() {
    this.refs.myComponentDiv.addEventListener('click', this.clickHandler);
  }

  componentWillUnmount() {
    this.refs.myComponentDiv.removeEventListener('click', this.clickHandler);
  }

  clickHandler() {
    this.setState({
      clicks: this.clicks + 1
    });
  }

  render() {
    let children = this.props.children;

    return (
      <div className="my-component" ref="myComponentDiv">
      <h2>My Component ({this.state.clicks} clicks})</h2>
      <h3>{this.props.headerText}</h3>
    {children}
    </div>
    );
  }
}
```

Given the code defined above, can you identify two problems?
