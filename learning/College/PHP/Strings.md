```php
<?php
$string1 = 'Hello, World!'; // Single-quoted string
$string2 = "Hello, World!"; // Double-quoted string with variable interpolation

// Accessing characters in a string
echo $string2[0]; // Output: H
echo $string2[7]; // Output: W
?>
```

#### `strpos()`
```php
<?php
$text = "Hello, welcome to PHP programming!";
$position = strpos($text, "PHP");
if ($position !== false) {
    echo "Found at position: $position"; // Output: Found at position: 18
}
?>
```

#### `str_replace()`
```php
<?php
$text = "Hello, World!";
$newText = str_replace("World", "PHP", $text);
echo $newText; // Output: Hello, PHP!
?>
```

#### Concatenation
Use the `.` operator to concatenate strings
```php
<?php
$firstName = "Tushar";
$lastName = "Sharma";
$fullName = $firstName . " " . $lastName;
echo $fullName; // Output: Tushar Sharma
?>
```

#### Interpolation
```php
<?php
$age = 25;
echo "I am $age years old."; // Output: I am 25 years old.
?>
```

using `printf()` and `sprintf()`
- `printf()`: Outputs a formatted string.
- `sprintf()`: Returns a formatted string (without printing it).
```php
<?php
$number = 42.5678;
printf("Formatted number: %.2f", $number); // Output: Formatted number: 42.57
$formattedString = sprintf("Price: $%.2f", $number);
echo $formattedString; // Output: Price: $42.57
?>
```

#### Library functions
- `strlen($string)`: Returns the length of a string.
- `strtoupper($string)`: Converts a string to uppercase.
- `strtolower($string)`: Converts a string to lowercase.
- `ucfirst($string)`: Capitalizes the first character of a string.
- `ucwords($string)`: Capitalizes the first character of each word in a string.
- `trim($string)`: Removes whitespace from both ends of a string.
- `ltrim($string)`: Removes whitespace from the beginning of a string.
- `rtrim($string)`: Removes whitespace from the end of a string.
- `str_pad($string, length, pad_string)`: Pads a string to a specified length.
- `explode(delimiter, string)`: Splits a string by a delimiter into an array.
- `implode(glue, array)`: Joins array elements into a string with a specified glue.
- `substr($string, start, length)`: Extracts a substring.
- `strrev($string)`: Reverses a string.
- `str_repeat($string, times)`: Repeats a string multiple times.