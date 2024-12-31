- Node.js identifies several types of events. Each event can be attached to a callback function.
- The Node.js runtime is always listening to events that may occur. 
- When any event that it can identify occurs, its attached callback function is executed.
- Node.js API includes events module, consisting mainly the `EventEmitter` class.
- An `EventEmitter` object triggers a certain type of event.
- You can assign one or more callbacks (listeners) to a certain type of event. 
- Whenever that event triggers, all the registered callbacks are fired one by one in order to which they were registered.

Example
```JavaScript
let events = require('events');
let eventEmitter = new event.EventEmitter();

eventEmitter.on("connection", ()=>{
	console.log("Connected successfully");
});

eventEmitter.on('data_recieved', ()=>{
	console.log("Data recieved successfully");
});

eventEmitter.emit("connection");
eventEmitter.emit("data_recieved");
```


