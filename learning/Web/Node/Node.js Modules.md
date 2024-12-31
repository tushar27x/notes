- A module in Node.js is a collection of independent and reusable code that can be imported into any Node.js application.
- It enables a modular structure approach for developing Node.js applications.
- Instead of putting all the functions, classes and methods into a single `.js`, these resources can be arranged in separate files based on their relevance.

### Types of Modules

1. __*Third-party modules*__
- These modules are developed by independent developers and made available for use on the NPM repository.
- You can install these modules either locally or globally
```shell
npm install express -g // install globally
or 
npm install express -save //install locally
```

2. __*Built-in modules*__
- Node.js comes with a bundle of core modules, that perform important server-side tasks, such as managing event loop, perform file IO and operating system-specific functions etc. 
- These modules are pre-installed, but we have to import them into our project file in order to use them 
```JavaScript
const fs = require('fs');
```

3. __*Local modules*__
- A local module is `.js` file that stores definitions f one or more functions or classes required for you application.
- Such a module is present locally in the same Node.js application folder.
- They also need to be imported in order to use them.

```javascript
exports.power = function powerval( x, y) { 
	var val = Math.pow(x,y); 
	return val; 
} 
exports.root = function rootval(x,y) { 
	var val = Math.sqrt(x); 
	return val; 
} 
exports.log = function logval(x) { 
	var val = Math.log10(x); 
	return val; 
}
```
