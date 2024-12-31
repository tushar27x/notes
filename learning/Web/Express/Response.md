The `res` object represents the HTTP response that an Express app sends when it gets an HTTP request.

```javascript
app.get('/user/:id', (req, res) => {
  res.send(`user ${req.params.id}`)
})
```

## some of the properties include

### `res.send()`

```javascript
app.get('/',(req,res)=>{
	res.send("<h1>Welcome</h1>");
});
```

### `res.sendFile()`

```javascript
app.get('/',(req,res)=>{
	res.sendFile(path.join(__dirname,"/index.html"));
});
```
#### `res.json([body])`

```javascript
app.get('/',(req,res)=>{
	res.json({
		name: req.body.username,
		age: req.body.age
	});
})
```


### `res.redirect()`

```javascript
app.get('/',(req,res)=>{
	res.send("<h1>Welcome</h1>");
});

app.get("/login", (req,res)=>{
	// perform login operations
	res.redirect('/');
})
```


There are more properties associated with `res` object refer documentation for them.