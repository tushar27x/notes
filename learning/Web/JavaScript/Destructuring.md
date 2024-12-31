## Destructuring Arrays
When Destructuring arrays, the order that variables are declared is important.

```javascript
function calculate(a, b) {
	const add = a + b;
	const subtract = a - b;
	const multiply = a * b;
	const divide = a / b;
	
	return [add, subtract, multiply, divide];
}

const [add, subtract, multiply, divide] = calculate(4, 7);
```


## Destructuring Objects
```javascript
const vehicleOne = {
  brand: 'Ford',
  model: 'Mustang',
  type: 'car',
  year: 2021, 
  color: 'red'
}

myVehicle(vehicleOne);

function myVehicle({type, color, brand, model}) {
	const message = 'My ' + type + ' is a ' + color + ' ' + brand + ' ' + model + '.';
}
```
