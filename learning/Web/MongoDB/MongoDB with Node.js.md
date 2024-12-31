[[MongoDB]]

### Installation of MongoDB Package
```shell
npm i mongodb
```

```javascript
const mongodb = require("mongodb");
require('dotenv').config();

const client = mongodb.MongoClient;
const uri = process.env.MONGODB_URI || "mongodb://localhost:27017/mydb;

client.connect(uri, (err,db){
	if(err){
		throw err;
	}
	const dbo = db.db("mydb"); // database object
	dbo.createCollection("user",(err,res)=>{
		if(err){
			throw err;
		}
		console.log("Collection created");
	})

	const doc = {
		username: "John Doe",
		age: 31
	}
	dbo.collection("users").insertOne(doc, (err,res)=>{
		if(err){
			throw err;
		}
		console.log("Inserted Document:" + doc);
	})
	

	db.close()
})
```

```javascript
//finding all documents
const mongodb = require("mongodb");
require('dotenv').config();

const client = mongodb.MongoClient;
const uri = process.env.MONGODB_URI || "mongodb://localhost:27017/mydb";

client.connect(uri, (err,db){
	if(err){
		throw err;
	}
	const dbo = db.db("mydb"); // database object
	dbo.collections("users").find({}).toArray((err,res)=>{
		if(err) throw err;
		console.log(res);
	})
	

	db.close()
})
```

[[Mongoose]]

