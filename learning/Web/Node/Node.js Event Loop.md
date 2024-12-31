Some key points about JavaScript to remember before we start learning about Event loop

- **JavaScript is synchronous** 
- **JavaScript is blocking**
- **JavaScript is single-threaded**

These properties of JavaScript pose a problem when developing application which require data fetching as we have to wait for data to be fetched before further code execution.

To implement Asynchronous programming using JavaScript Node.js is used
Node.js provides a runtime to run JavaScript code outside of a browser.

Node.js consists of three major components:
- **External dependencies** — such as V8, libuv, crypto — required by Node.js for its functioning
- **C++ features** that provide for functionality such as file system access and networking
- A **JavaScript library** that provides functions and utilities to tap into the C++ features from your JavaScript code

## Libuv

- It is an open source library written **C** 
- It's role is to support handling of asynchronous operation.
- For async operations like reading a file that has no native OS support, libuv relies on its thread pool to ensure that the main thread is not blocked.

## Event loop


![[event loop.webp]]

The event loop consists of 6 different queues
1. **timer queue** -> contains callbacks associated with `setTimeout()` and `setInterval()`.
2. **I/O queue** -> contains callbacks associated with all async method such as methods associated with `fs` and `http` modules.
3. **check queue** -> contains callbacks associated with `setImediate` functions, specific to Node.js.
4. **close queue** -> contains callbacks associated with the close events of an async task.

Beside these 4 there are 2 microtask queues:
6. **next tick queue** -> contains callbacks associated with `process.nextTick()` function.
7. **Promise queue** -> contains callbacks associated with native promises in JavaScript.


Within the event loop, the sequence of execution follows certain rules. There are quite a few rules to wrap your head around, so let's go over them one at a time:

1. Any callbacks in the microtask queue are executed. First, tasks in the `nextTick` queue and only then tasks in the promise queue.
2. All callbacks within the timer queue are executed.
3. Callbacks in the microtask queue (if present) are executed after every callback in the timer queue. First, tasks in the `nextTick` queue, and then tasks in the promise queue.
4. All callbacks within the I/O queue are executed.
5. Callbacks in the microtask queues (if present) are executed, starting with `nextTick` Queue and then Promise queue.
6. All callbacks in the check queue are executed.
7. Callbacks in the microtask queues (if present) are executed after every callback in the check queue. First, tasks in the `nextTick` queue, and then tasks in the promise queue.
8. All callbacks in the close queue are executed.
9. For one final time in the same loop, the microtask queues are executed. First, tasks in the `nextTick` queue, and then tasks in the promise queue.

### Q) When an async task completes in libuv, at what point does Node decide to run the associated callback function on the call stack?

Answer: Callback functions are executed only when the call stack is empty.

### Q) Does Node wait for the call stack to be empty before running the callback function, or does it interrupt the normal flow of execution to run the callback function?

Answer: The normal flow of execution will not be interrupted to run a callback function.

### Q) What about other async methods like `setTimeout` and `setInterval`, which also delay the execution of a callback function?

Answer: `setTimeout` and `setInterval` callbacks are given first priority.

### Q) If two async tasks such as `setTimeout` and `readFile` complete at the same time, how does Node decide which callback function to run first on the call stack? Does one get priority over the other?

Answer: Timer callbacks are executed before I/O callbacks, even if both are ready at the exact same time.