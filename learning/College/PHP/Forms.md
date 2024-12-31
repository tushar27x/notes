#### Handling HTML form with PHP
```html
<form method="POST" action="process.php">
	<label for="name">Name:</label>
	<input type="text" name="name" id="name">
	<input type="submit" value="Submit">
</form>
```

```php
// process.php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
	$name = $_POST['name'];
	echo "Hello, $name!";
}
```

##### Handling multi-value fields
```html
<form method="POST" action="process.php">
	<label>Select Fruits:</label><br>
	<input type="checkbox" name="fruits[]" value="Apple">Apple<br>
	<input type="checkbox" name="fruits[]" value="Banana">Banana<br>
	<input type="checkbox" name="fruits[]" value="Cherry">Cherry<br>
	<input type="submit" value="Submit">
</form>
```

```php
if (isset($_POST['fruits'])) {
	foreach ($_POST['fruits'] as $fruit) {
		echo $fruit . "<br>";
	}
}
```
### PHP form handling

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Learning PHP</title>
</head>
<body>
    <form action="form.php" method="POST">
        <input type="text" name="name" placeholder="Enter name"/>
        <input type="submit"/>
    </form>
</body>
</html>
```

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form Data</title>
</head>
<body>
    <h1>Welcome <?php echo $_POST['name']; ?>
    </h1>
    
</body>
</html>
```

### GET v/s POST

- both GET and POST creates an array (e.g. array( key1 => value1, key2 => value2, key3 => value3, ...)).
- Both GET and POST are treated as $_GET and $_POST.
- These are superglobals, which means that they are always accessible, regardless of the scope.
- $_GET is an array of variables passed to the current script via the URL parameters.
- $_POST is an array of variables passed to the current script via the HTTP POST method.
- Information sent from a form with the GET method is **visible to everyone.** GET also has limits on the amount of information to send. The limitation is about 2000 characters.

    <aside> 💡 GET should NEVER be used for sending passwords or other sensitive information!
    
    </aside>
   
- Information sent from a form with the POST method is **invisible to others** and has **no limits** on the amount of information to send.
