- `props` → props are a way to pass data or properties from one component to other components. Props are objects which can be used inside a component.
- `state` → state is the real time data available to use within that component only. A state is variable that is declared inside a component and can only be used within the components.

| Props                                                 | State                                               |
| ----------------------------------------------------- | --------------------------------------------------- |
| data passed from one component to another             | internal data of the component                      |
| it is immutable                                       | it is mutable                                       |
| they can be used with class and functional components | The state can be used only with stateful components |
| props are read only                                   | state is both read and write                        |




```jsx
// Example of state in a react class component
import React from "react";
class MyComponent extends React.Component {
  constructor() {
    super();
    this.state = {
      text: "",
    };
  }

  render() {
    return (
      <div>
        <input
          type="text"
          placeholder="Enter text"
          value={this.state.text}
          onChange={(e) => {
            this.setState({ text: e.target.value });
          }}
        />
        <h3>{this.state.text}</h3>
      </div>
    );
  }
}
```

```jsx
// Example of state in a react function component
const MyComponent = ()=>{
	const [text, setText] = useState('test');
	return(
		<div>
			<input
        type="text"
        placeholder="Enter text"
        value={this.state.text}
        onChange={(e) => {
          this.setState({ text: e.target.value });
        }}
       />
			<h3>{text}</h3>
		</div>
	)
}
```