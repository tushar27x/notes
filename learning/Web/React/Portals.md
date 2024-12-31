React portal helps you to render components outside of the parents DOM hierarchy into a different DOM subtree.

They are useful in scenarios where you need to render content outside of the regular DOM structure, such as modals, or any overlay that need to appear above all other content on the page without begin constrained by the DOM hierarchy.

```jsx
import ReactDOM from 'react-dom';
const Modal = ()=>{
	return(
		<>
		<h1>Modal</h1>
		<p>This is a modal</p>
		</>
	);
}

const App = ()=>{
	return(
		<h1> example of a portal </h1>
		{
			ReactDOM.createPortal(
				<Modal />,
				document.getElementById('modal-root')
			);
		}
	);
}
```