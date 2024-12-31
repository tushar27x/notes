- Routing refers to how an application endpoints respond to the client requests.
- You define routing methods of the Express `app` object that correspond to HTTP method, for example, `app.get()` to handle GET requests and `app.post` to handle POST requests.
- These routing methods specify a callback function (sometimes called “handler functions”) called when the application receives a request to the specified route (endpoint) and HTTP method.

### Route Methods
A route method is derived from one of the HTTP methods, and is attached to an instance of the `express` class.

The following code is an example of routes that are defined for the GET and the POST methods to the root of the app.
```javascript
app.get('/', (req, res) => {
  res.send('GET request to the homepage')
})

app.post('/', (req, res) => {
  res.send('POST request to the homepage')
})
```

There is a special routing method, `app.all()`, used to load middleware functions at a path for _all_ HTTP request methods.
```javascript
app.all('/secret', (req, res, next) => {
  console.log('Accessing the secret section ...')
  next() // pass control to the next handler
})
```

### Route Paths
Route paths, in combination with a request method, define the endpoints at which requests can be made. Route paths can be strings, string patterns, or regular expressions.
```javascript
app.get('/about', (req, res) => {
  res.send('about')
})
```

### Route Parameters
Route parameters are named URL segments that are used to capture the values specified at their position in the URL. The captured values are populated in the `req.params` object, with the name of the route parameter specified in the path as their respective keys.
```javascript
app.get('/users/:userId/books/:bookId', (req, res) => {
  res.send(req.params)
})
```


