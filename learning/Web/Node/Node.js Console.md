- Node.js console module is a global object that provides a simple debugging console similar to JavaScript to display different levels of message.
- It is provided by web browsers.
- It contains two components:
	 1. **Console class**: The console class methods are `console.log()`, `console.err()` and `console.warn()`.
	 2. **global console**: It is called without calling `require('console');`.

*Example of Global Console object*

```JavaScript
console.log("This is and example of log() method");
console.err(new Error("An Error has occurred"));
console.warn("This is an example of warn() method")
```

Apart from `log()`,`warn()` and `error()` a few other methods are also available
- `console.count()`: It is used to count the number of times a specific label has been called.
- `console.clear():` It is used to clear the console history.
- `console.info():` It is used to write a messages on console and it is an alias of console.log() method.
- `console.time():` It is used to get the starting time of an action.
- `console.timeEnd():`It is used to get the end time of specific action.
- `console.dir():` It use `util.inspect()` on object and prints the resulting string to `stdout`.