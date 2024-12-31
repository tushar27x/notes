```php
<!DOCTYPE html>
<html>
<head>
    <title>PHP Decisions and Loops</title>
</head>
<body>

<h1>Menu</h1>
<ul>
<?php
$menuItems = ["Home", "About", "Services", "Contact"];

foreach ($menuItems as $item) {
    echo "<li>$item</li>";
}
?>
</ul>

<h2>Greeting</h2>
<p>
<?php
$timeOfDay = "evening";

if ($timeOfDay == "morning") {
    echo "Good morning!";
} elseif ($timeOfDay == "afternoon") {
    echo "Good afternoon!";
} else {
    echo "Good evening!";
}
?>
</p>

</body>
</html>
```
