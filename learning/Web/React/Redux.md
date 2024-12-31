## “Redux is a predictable state container for JavaScript apps.”

#### Why use Redux?

An application has its state, which can be a combination of the states of its internal components.

The task of handling multiple states form multiple components efficiently can become challenging when the application grows in size.

This is where Redux comes into the picture. Being a state management library, Redux will basically store and manage all the applications states.

#### What makes Redux predictable?
    
Given an initial state, with a specific list of actions in specific order, it’ll always provide us with the exact same final state of the entity. This is how Redux makes state management predictable.

Example→ In an e-commerce application, starting with an empty cart if the user adds one item the number of items in the cart will be increased by 1, if the user chooses to add more items in the cart then the total number of items will be increased by 1 each time.

> _"Actions can be recorded and replayed later, so this makes state management predictable. With the same actions in the same order, you're going to end up in the same state."_

To make a change in the state of the application, we need to `dispatch` an `action` which describes what changes we want to make in the state. These `actions` are then consumed by `reducers` which accepts two arguments:

1. current state
2. action

and return the updated instance of the state.

### Using Redux in our application

- Installation

```bash
npm i react-redux @reduxjs/toolkit
```

- `src/store.js`

```jsx
import { configureStore } from '@reduxjs/toolkit'
import counterReducer from './features/counterSlice'

export const store = configureStore({
  reducer: {
	counter: counterReducer,
  },
})
```

- `src/features/counterSlice.js`

```jsx
import {createSlice} from '@reduxjs/toolkit'

const initialState = {
	value: 0
}
const counterSlice = createSlice({
	name: "counter",
	initialState,
	reducers:{
		increment: (state) =>{
			state.value += 1;
		} ,
		decrement : (state) =>{
			state.value -= 1;
		}
	}
});

export const {increment, decrement} = counterSlice.actions;
export default counterSlice.reducer;
```

- `src/components/Card.jsx`


```jsx
import React from 'react'
import {useSelector} from 'react-redux'

const Card = () => {
const countValue = useSelector(state => state.counter.value)
return (
<div>
	{countValue}
</div>
)
}

export default Card;
```

- `src/index.js`

```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';
import reportWebVitals from './reportWebVitals';
import {store} from './store'
import {Provider} from 'react-redux'
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
	<Provider store={store}>
	<React.StrictMode>
		<App />
	</React.StrictMode>
	</Provider>
);
reportWebVitals();

```

- `src/App.js`

```jsx
import './App.css';
import  Counter from './components/Counter';
import Card from './components/Card'
function App() {
  return (
	<div className="App">
	  <Card />
	  <Counter />
	</div>
  );
}

export default App;

```