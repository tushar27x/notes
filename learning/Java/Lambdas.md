*They are basically instances of functional interfaces*

**Functional Interface** -> an interface that has only one abstract method. These are also called as SAM (Single Abstract Method) interfaces.

You can define a Functional Interface by using the `@FunctionalInterface` annotation.
These interfaces *can* still contain static methods or default methods but they need to have **exactly one** abstract method.

**Syntax**

```java
(parameter) -> {
	// return statement
}
```

**Example**

```java
(s)->{
	return "hello "+ s;
}
```

OR

```java
s -> "hello "+ s;
```


#### Using Lambda expressions

```java
// Printable interface
@FunctionalInterface
public interface Printable{
	void print(s);
}

// Main
public class Main{
	public static void main(String[] args){
		Printable lambdaPrintable = (s) -> "hello "+s;
		printThing(lambdaPrintable);
	}
}

public static void printThing(Printable thing){
	thing.print("!");
}
```