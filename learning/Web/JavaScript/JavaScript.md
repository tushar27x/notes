- JavaScript is a scripting or programming language that allows you to implement complex features on web pages
- JavaScript is a lightweight interpreted programming language. The web browser receives the JavaScript code in its original text form and runs the script from that.
- From a technical standpoint, most modern JavaScript interpreters actually use a technique called **just-in-time compiling** to improve performance; the JavaScript source code gets compiled into a faster, binary format while the script is being used, so that it can be run as quickly as possible. However, JavaScript is still considered an interpreted language, since the compilation is handled at run time, rather than ahead of time.

### Intrinsic Event handling

Intrinsic event handling, also known as inline event handling, refers to the practice of attaching event handlers directly to HTML elements within the markup itself. This is done by using event attributes such as **`onclick`**, **`onmouseover`**, **`onkeydown`**, etc., directly within the HTML tags.

```html
<button onclick="alert('Button clicked!')">Click me</button>
```
 
 ## Modifying element style
```javascript
const myBox = document.getElementById('myBox');
myBox.style.backgroundColor = 'red';
myBox.style.width = '150px';
myBox.style.height = '150px';
```

[[Literals]]
[[Lists]]
[[Destructuring]]
[[Spread Operator]]
[[ES5 vs ES6]]
    