- Since React is used to create single page applications, i.e. the components are rendered dynamically onto the same page based on user’s input and requirement.
- For creating routes on our SPA we make use of a `npm` package called `react-router-dom`
- to install `react-router-dom` run the following command in your command line.
```bash
npm i react-router-dom
```

- After your installation has completed, you can start using the package in the following way.
```jsx
// index.js
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';
import About from './components/About';
import Home from './components/Home';
import Profile from './components/Profile';
import {createBrowserRouter, RouterProvider} from 'react-router-dom'
import Error from './components/Error';
const router = createBrowserRouter([
	{
		path: '/',
		element: <Home />,
		errorElement: <Error />
	},
	{
		path: '/home',
		element: <Home />
	},
	{
		path: '/about',
		element: <About />
	},
	{
		path: '/profile',
		element: <Profile />
	}
	])
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
	<App />
	<RouterProvider router={router} />
  </React.StrictMode>
);

```

```jsx
// App.js

function App() {
  return (
	<div className="App">
		<h1>Router</h1>
		<nav>
		  <ul>
			<li><a href='/home'>Home</a></li>
			<li><a href='/about'>About</a></li>
			<li><a href='/profile'>Profile</a></li>
		  </ul>
		</nav>
	</div>
  );
}
export default App;
```

- As you can observer that our `<App />` component is rendering an undefined list that consists of the links to different components.

- In our `index.js` file we have created a browser router using the package we have just installed and defined the paths to various components.