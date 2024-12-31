
A component has 3 phases

### 1. **Mounting phase**

It refers to the phase when the component is being inserted in the DOM. During this phase, several lifecycle methods are invoked by React to enable the developer to configure the component, set up any necessary state or event listeners, and perform other initialization tasks.
The mounting phase has following lifecycle methods that are called in order:

1. `constructor()` ⇒ it is called when the component is first created. It is used to initialize the component’s state and bind methods to the component’s instance.
```jsx
import React from "react";
class Button extends React.Component {
  constructor() {
	super();
	this.state = {
	  count: 0,
	};
	this.handleClick = this.handleClick.bind(this);
  }
  handleClick() {
	this.setState((prevState) => ({
	  count: prevState.count + 1,
	}));
  }
}

export default Button;

```

2. `render()` ⇒ it is responsible for generating the component’s virtual DOM representation based on its current props and state. It is called every time the component need to be re-rendered, either because of the change in props or state or the parent component has been changed.

```jsx
render() {
	return (
	  <div>
		<h3>Button clicked {this.state.count} times</h3>
		<button onClick={this.handleClick}>Click Me</button>
	  </div>
	);
}
```

3. `getDerivedStateFromProps(props,state)` ⇒ this method is invoked after `constructor()` and before `render()` method. It takes two parameters `state` (current state) & `props` (updated props) and return an object representing the updated state of the component or `null` if no state updated is necessary.
```jsx
class MyComponent extends React.Component {
	constructor(props) {
		super(props);
		this.state = {
		  someState: props.someValue
		};
	}
	static getDerivedStateFromProps(nextProps, prevState) {
	// Compare nextProps to prevState or do any other necessary operations
	// and return an object to update the state, or null if no update is needed.
		if (nextProps.someValue !== prevState.someValue) {
		  return {
			someState: nextProps.someValue
		  };
		}
		return null; // No state update is needed
	}
	
	render(){ 
		return <div>{this.state.someState}</div>;
	}
}
```

4. `componentDidMount()` ⇒ this method is called once the component has been mounted into the DOM. It is typically used to set up any necessary event listeners or timers, perform any necessary API calls or data fetching, and perform other initialization tasks that require access to the browser's DOM API.
```jsx
import React from "react";
class Button extends React.Component {
	constructor(props) {
		super(props);
		this.state = {
		  count: 0,
		};
		this.handleClick = this.handleClick.bind(this);
	}
	
	componentDidMount(): void {
		setTimeout(() => {
			this.setState({
				count: 10,
			});
		}, 3000);
	}
	
	handleClick() {
		this.setState((prevState) => ({
		  count: prevState.count + 1,
		}));
	}
  render() {
	return (
		<div>
			<h3>Button clicked {this.state.count} times</h3>
			<button onClick={this.handleClick}>Click Me</button>
		</div>
	);
  }
}

export default Button;

```
    
### 2. **Updating phase**

This phase occurs when a components `state` or `props` change. The methods invoked in this phase are:
1. `shouldComponentUpdate(nextProps, nextState)` ⇒ It takes two arguments and returns a Boolean value determining whether a components needs to updated or not.

```jsx
import React from "react";
class Button extends React.Component {
	constructor(props) {
		super(props);
		this.state = {
		  count: 0,
		};
		this.handleClick = this.handleClick.bind(this);
	}
	handleClick() {
		this.setState((prevState) => ({
			count: prevState.count + 1,
		}));
	}
  
	// Makes sure that component does not get updated when the count value
	// is more than 5.
	shouldComponentUpdate(nextProps, nextState) {
		return nextState.count <= 5;
	}
	render() {
		return (
			<div>
				<h3>Button clicked {this.state.count} times</h3>
				<button onClick={this.handleClick}>Click Me</button>
			</div>
		);
	}
}

export default Button;

```

2. `componentWillUpdate()` ⇒ it gets called just before a component’s update cycle starts. It receives the next prop and state as arguments.

```jsx
componentWillUpdate(nextProps, nextState) {
	if (nextState.count !== this.state.count) {
	console.log(`Count is about to update from ${this.state.count} to ${nextState.count}.`);
	}
}
```

this method is not recommended for updating the state, as it can cause an infinite loop of rendering. It is primarily used for tasks such as making API calls, updating the DOM, or preparing the component to receive new data.`componentWillUpdate()` is often used in conjunction with `componentDidUpdate()` to handle component updates.

3. `componentDidUpdate()` ⇒ The `componentDidUpdate()` method is a lifecycle method in React that is called after a component has been updated and re-rendered.

```jsx
componentDidUpdate(prevProps, prevState) {
	if (prevState.count !== this.state.count) {
	  console.log('Count has been updated:', this.state.count);
	}
}
```

4. `getSnapshotBeforeUpdate()` ⇒ The `getSnapshotBeforeUpdate()` method is called just before the component's UI is updated. It allows the component to capture some information about the current state of the UI, such as the scroll position before it changes. This method returns a value that is passed as the third parameter to the `componentDidUpdate()` method.

```jsx
getSnapshotBeforeUpdate(prevProps, prevState) {
  document.getElementById("div1").innerHTML =
  "Before the update, the favorite was " + prevState.favoritefood;
}
componentDidUpdate() {
  document.getElementById("div2").innerHTML =
  "The updated favorite food is " + this.state.favoritefood;
}
render() {
  return (
	<div>
	  <h1>My Favorite Food is {this.state.favoritefood}</h1>
	  <div id="div1"></div>
	  <div id="div2"></div>
	</div>
  );
}
```

### 3. **Unmounting phase**

- `componentWillUnmount()` ⇒ this method is called just before the component is removed from the DOM. It allows you to perform any necessary cleanup, such as cancelling timers, removing event listeners, or clearing any data structures that were setup during the mounting phase. After the component has been unmounted, it cannot be mounted again. If the component has to re-rendered we have to create a new instance of it.