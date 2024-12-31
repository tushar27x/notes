- JSX stands for JavaScript XML.
- It allows us to write HTML in React.
- It is a syntax extension to JavaScript.
- It is a template language which comes with full functionality of JavaScript
- **Rules for JSX:**
1. **Return single root element** - To return multiple elements from a component, wrap them with a single parent tag, example

```jsx
export default function MyComponent(){
	return (
		<div>
			<h1>This is a component<h1>
			<p>We are returning a single parent component</p>
		</div>
	)
}
```

instead of returning a `<div></div>` element we can also make use of react **fragments(** `<></>` **).**

2. **Close all tags -** JSX requires to be explicitly closed, i.e. even the self closing tags that are used in HTML require a closing tag while writing JSX components. example:

```jsx
<img src="profile.png" alt="profile" />
```

3. **camelCase all things -** JavaScript has a limitation of variable names, and when writing JSX it is very easy to confuse HTML attributes with JavaScript reserved keywords. For example: `class` has different meanings from the perspective of HTML code and JavaScript code. JSX solves this by forcing you write HTML and SVG attributes in camelCase. Example:

1. `class` ⇒ `className`
2. `onclick` ⇒ `onClick`