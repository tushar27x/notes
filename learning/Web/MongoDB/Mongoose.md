- it is a `npm` package that is used to optimize working with MongoDB databases in express.js applications

```javascript
const express = require('express');
const mongoose = require('mongoose');
const bodyParser = require('body-parser');
require('dotenv').config;

const app = express();
app.use(bodyParser.urlEncoded({extended:true}));
const URI = process.env.URI;
mongoose.connect(URI).then(()=>{
	console.log("Connected to Database successfully!");
});

const userSchema = new mongoose.Schema({
	username: String,
	email: String,
	age: Number,
});

const User = mongoose.Model("user", userSchema);

app.get('/add-user', (req,res)=>{
	try{
		const {username, email, age} = req.body;
		const newUser = new User({username, email, age});
		await newUser.save();
		res.status(200).json({"message":"User created successfully"})
	}catch(err){
		res.status(500).json({"message":err});
	}
});

app.listen(3000);
```
