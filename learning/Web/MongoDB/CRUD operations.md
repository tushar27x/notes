
#### `insertOne()` & `insertMany()`
 ```JSON
 db.users.insertOne({
	 username: "Tushar Sharma",
	 email: "sharmatushar2703@gmail.com",
	 age: 20,
 })
```

```json
 db.users.insertmany([
	 {
		 username: "Tushar Sharma",
		 email: "sharmatushar2703@gmail.com",
		 age: 20,
	 },
	 {
		 username: "John Dow",
		 email: "johndoe@gmail.com",
		 age: 30,
	 }
 ])
```

#### `find()` and `findOne()`
It return all the documents in the collection
```json
db.users.find()
```

```json
db.users.findOne({username: "Tushar Sharma"})
```

### `updateOne()`
```json
db.users.updateOne({username: "Tushar Sharma"}, {$set:{age: 21}})
```
In case we want to insert the document if not found, we can use `upsert` property
```json
db.users.updateOne(
	{username: "Tushar Sharma"}, 
	{
		$set:{
			{
				username: "Tushar Sharma",
				email: "sharmatushar2703@gmail.com",
				age: 21
			}
		}
	},
	{upsert: true}
)
```


#### `deleteOne()` and `deleteMany()`
```json
db.users.deleteOne({username:"John Doe"})
```