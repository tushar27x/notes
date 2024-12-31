
## Intro
- It emphasizes the use of pure functions that don't have side effects and always return the same output for a given input.
- interfaces -> `java.util.function.Function`, `java.util.function.BiFunction`, 
- It helps to write code that is concise and expressive. 

# `Function<T, R>`

![[Pasted image 20240901190123 2.png]]

- It takes the input of type `T` and produces an output of type `R`.
- It has a single abstract method, `apply()` which takes an argument of a specified type and returns a result of a specified type.

```java
class Greet{
	private final Function<String> greet = (name) ->{
		return "hello"+ name;
	}
}
```

## `BiFunction<T, U, R>`

![[Pasted image 20240901190503 2.png]]

- It takes two inputs  of type `T` and `U` and produces the result of type `R`.
```java
class Greet{
	private final Function<String, String, String> greet = (fName, lName) ->{
		return "hello "+ fname+ " "+lName;
	}
```

