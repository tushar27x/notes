```php
<?php
function greet($name) {
    echo "Hello, $name!";
}
?>
```

```php
<?php
greet("Tushar")
?>
```


#### Call by value
```php
<?php
function addOne($num) {
    $num++;
    echo "Inside function: $num<br>"; // Inside function: 6
}

$original = 5;
addOne($original); 
echo "Outside function: $original"; // Outside function: 5
?>
```

#### Call by reference
```php
<?php
function addOne(&$num) { // &symbol for passing reference
    $num++;
}

$original = 5;
addOne($original);
echo $original; // Output: 6
?>
```

#### Recursion
```php
<?php
function factorial($n) {
    if ($n <= 1) {
        return 1; // Base case
    } else {
        return $n * factorial($n - 1); // Recursive call
    }
}

echo factorial(5); // Output: 120 (5 * 4 * 3 * 2 * 1)
?>
```
