#### Variables in PHP

- A variable starts with the `$` sign, followed by the name of the variable
- A variable name must start with a letter or the underscore character
- A variable name cannot start with a number
- A variable name can only contain alpha-numeric characters and underscores (A-z, 0-9, and _ )
- Variable names are case-sensitive (`$age` and `$AGE` are two different variables)
- PHP supports the following data types:
	- String
	- Integer
	- Float (floating point numbers - also called double)
	- Boolean
	- Array
	- Object
	- NULL
	- Resource → The special resource type is not an actual data type. It is the storing of a reference to functions and resources external to PHP.
- To get the data type of variables `var_dump()` can be used

#### Output variables

The PHP `echo` statement is often used to output data to the screen.

The following example will show how to output text and a variable:

```php
$name= "Tushar";
echo "My name is $name";
//or
echo "My name is " . $name ;
```

<aside> 💡 PHP is a loosely typed language. PHP automatically associates a data type to the variable, depending on its value. Since the data types are not set in a strict sense, you can do things like adding a string to an integer without causing an error.

</aside>

#### Scope of variables

1. Global Scope

```php
$x = 5; // global scope

function myTest() {
  // using x inside this function will generate an error
  echo "<p>Variable x inside function is: $x</p>";
}
myTest();

echo "<p>Variable x outside function is: $x</p>";
```

2. Local Scope → variables declared within a function has local scope and can only be accessed within that function.

```php
function myTest() {
	$x = 5; // local scope
	echo "<p>Variable x inside function is: $x</p>";
}
myTest();

// using x outside the function will generate an error
echo "<p>Variable x outside function is: $x</p>";
```
3. Static scope → local variables declared with `static` keyword are stored in memory even after the function has finished executing.


### PHP echo and print

`echo` and `print` statements are used to output data to the screen.

| echo                         | print                      |
| ---------------------------- | -------------------------- |
| has no return value          | has a return value of 1    |
| can take multiple parameters | can take only one argument |
| faster than print            | slower than echo           |
