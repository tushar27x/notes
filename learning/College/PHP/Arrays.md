#### PHP array

An array stores multiple values in one single variable.

```php
//creating an array
$cars = array("Volvo", "BMW", "Toyota");
//or 
$cars = ["Volvo", "BMW", "Toyota"];
```

there are 3 types of arrays in PHP

1. Indexed Arrays → each items has an index number. By default, the first item has index 0.
```php
$cars = array("Volvo","BMW","Toyota");
echo $cars[1];
foreach ($cars as $x) {
echo "$x <br>";
}
```

2. Associative arrays → arrays that use named keys that you assign to them.
```php
$car = array("brand"=>"Ford","model"=>"Mustang","year"=>1964);
echo $car["model"];
foreach ($car as $x => $y) {
  echo "$x: $y <br>";
}
```

3. Multidimensional Arrays
```php
$cars = array (
  array("Volvo",22,18),
  array("BMW",15,13),
  array("Saab",5,2),
  array("Land Rover",17,15)
);
```

Remove array items
1. `array_splice()`
```php
$cars = array("Volvo", "BMW", "Toyota");
array_splice($cars, 1, 2);
```

2. `unset()`
```php
$cars = array("Volvo", "BMW", "Toyota");
unset($cars[1]);
```

3. `array_diff()`
```php
$cars = array(
	"brand" => "Ford", 
	"model" => "Mustang", 
	"year" => 1964
);
$newarray = array_diff($cars, ["Mustang", 1964]);
```

4. `array_pop()` → remove last element
```php
array_pop($cars);
```

5. `array_shift()` → removes first element
```php
array_shift($cars)
```

Sorting arrays:
- `sort()` - sort arrays in ascending order
- `rsort()` - sort arrays in descending order
- `asort()` - sort associative arrays in ascending order, according to the value
- `ksort()` - sort associative arrays in ascending order, according to the key
- `arsort()` - sort associative arrays in descending order, according to the value
- `krsort()` - sort associative arrays in descending order, according to the key

