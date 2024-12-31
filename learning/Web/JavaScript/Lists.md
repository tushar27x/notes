For rendering lists we can make use of the JavaScript array methods to manipulate an array of data.

1. `map()` :
```javascript
const employees = [
	{
		name: "Tushar",
		age: 21,
	},
	{
		name: "Riddhi",
		age: 19,
	},
	{
		name: "Rahul",
		age: 25,
	},
];

const empNames = employees.map(emp => { 
	return emp.name
}); 
console.log(empNames);

```

2. `filter()` :
```javascript
const employees = [
	{
		name: "Tushar",
		age: 21,
	},
	{
		name: "Riddhi",
		age: 19,
	},
	{
		name: "Rahul",
		age: 25,
	},
];

const empNames = employees.filter(emp => { 
	return emp.age > 19
}); 
console.log(empNames);
```

3. `every()` - returns `true` if all elements return `true` , else `false`
```javascript
const person = [
	{
		name: "Tushar",
		age: 21,
	},
	{
		name: "Riddhi",
		age: 17,
	},
	{
		name: "Rahul",
		age: 25,
	},
];
const isAdult = (emp) =>{
	if(emp.age>=18){
		return true;
	}
	return false;
}

const adults = person.every(isAdult); 
console.log(adults);
```
### Array Destructuring

```javascript
const info= ['Tushar','Sharma',20];
const [fname, lname, age] = info;
console.log(info) //(3) ['Tushar', 'Sharma', 20]
```

**Spread operator**

```jsx
const arr1 = [1,2,3];
const arr2 = [4,5,6];
const arr3 = [...arr1, ...arr2]; 
console.log(arr3); //(6) [1, 2, 3, 4, 5, 6]

const [num1, num2, ...rest] = arr3;
console.log(num1);
console.log(num2);
console.log(rest);
//Output
//(6) [1, 2, 3, 4, 5, 6]
// 1
// 2
// (4) [3, 4, 5, 6]
```