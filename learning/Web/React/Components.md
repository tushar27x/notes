## **Ways of writing components**

There are 3 ways of writing component in react

### 1. React Class Component

-  it is the oldest method of creating react components. It requires you inherit the `React.Components` class.

- When creating a class component it is mandatory to start the class name with an uppercase letter.
```jsx
class MyComponent extends React.Component{
	render(){
		return (
			<h1>Example of react class component</h1>
		}
	}
}
```

### 2. React functional Component

- It is the simples way to create react components.
- It makes it very easy to pass down `props` as arguments from parent components to child components.
- It also makes it very easy to keep track of the state of the component by enabling us to use `hooks`, which is not possible in react class components.
```jsx
export default function Parent(){
	return(
		<div>
			<h1>Parent Component</h1>
			<Child name="tushar"/>
		</div>
	)
}

function Child(props){
	return(
		<div>
			<h3>Hello {props.name} </h3>
		</div>
	)
}
```


### 3. React functional arrow components

1. It is similar to normal functional components in all respects except it uses the newer ES6 arrow function (lambda function),
```jsx
export default const MyComponent = ()=>{ 
	return( 
		<div> 
			<h1>Example of Arrow function </h1> 
		</div> 
	); 
}
```
