- Error boundaries are React components that catch JavaScript errors anywhere in their child component tree, log these errors and display a fallback UI instead of the component tree that crashed.
- An error boundary component is a class component.
- A class component becomes an error boundary if it defines either or both of the lifecycle methods
    - `getDerivedStateFromError()`
    - `componentDidCatch()`

```jsx
import React, { Component } from "react";
class ErrorBoundary extends Component {
	constructor(props) {
		super(props);
		this.state = { hasError: false };
	}
	static getDerivedStateFromError(error) {
		return { hasError: true };
	}
	
	componentDidCatch(error, info) {
		console.log(error, info);
	}
	
	render() {
		if (this.props.hasError) {
			return this.props.fallback;
		}
		return this.props.children;
	}
}

export default ErrorBoundary;
```

```jsx
//index.js
import { createRoot } from "react-dom/client";
import App from "./App";
import ErrorBoundary from "../ErrorBoundary";
const rootElement = document.getElementById("root");
const root = createRoot(rootElement);

root.render(
    <ErrorBoundary hasError={false} fallback={<h1>Something Went Wrong!</h1>}>
      <App />
    </ErrorBoundary>
);

```

- Error boundaries work like JavaScript `catch{}` blocks but for components.
- In most situations we wrap the entire component tree inside an error boundary component.
- Error boundaries only catch errors in the components below them in the tree.
