- acronym for Hypertext Preprocessor.
- PHP is a server-side scripting language designed specifically for web development.
-  Unlike client-side languages like JavaScript, which are executed on the user’s browser, PHP scripts run on the server.


#### Characteristics of PHP
- is executed in the server.
- can be integrated with many databases
- the only information that the client or browser knows is the result returned after executing the PHP script on the server and not the actual PHP codes present in the PHP file.
- It supports main protocols like HTTP Basic, HTTP Digest, IMAP, FTP, and others.

#### Working
- A user requests a PHP page via their web browser.
- The server processes the PHP code. The PHP interpreter parses the script, executes the code, and generates HTML output.
- The server sends the generated HTML back to the client’s browser, which renders the web page.

#### Syntax
```php
<?php
	your code
?>
```

Example
```php
<!DOCTYPE html>
<html>
   
<head>
    <title>PHP Hello World</title>
</head>
   
<body>
    <?php echo "Hello, World! This is PHP code";?>
</body>

</html>
```

#### Features

1. Dynamically typed
2. Cross Platform
3. Server-Sider Rendering
4. Database integration

| Advantages       | Disadvantages                             |
| ---------------- | ----------------------------------------- |
| Open Source      | Inconsistent in naming                    |
| Easy to learn    | Security concerns                         |
| Web integration  | Scalability challenges                    |
| Database support | Not suitable for large scale applications |
| Cross platform   | Limited OOP support                       |
| Large community  |                                           |
