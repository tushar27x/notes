# Functional Chaining

- In Java FP, function chaining is often used to transform data in a series of steps, where each step applies a specific transformation to the data and passes it on to the next step in the chain.
- Each function in the chain is defined as a separate instance of the Function interface.
- This allows for a series of transformations to be applied to the data, one after another, until the final result is produced.

# `andThen()`

- This method takes a sequence of two functions and applies them in succession, using the output of the first function as the input to the second function.

```java
public class FunctionChainingExample {

    static Logger logger = Logger.getLogger(FunctionChainingExample.class.getName());

    private static Function<Integer, Integer> multiply = x -> x * 2;

    private static Function<Integer, Integer> add = x -> x + 2;

    private static Function<Integer, Unit> logOutput = x -> {
        logger.info("Data:" + x);
        return Unit.unit();
    };

    public static Unit execute(Integer input) {
        Function<Integer, Unit> pipeline = multiply
                                               .andThen(add)
                                               .andThen(logOutput);
        return pipeline.apply(input);
    }

    public static void main(String[] args) {
        execute(10);
    }

}
```

``` 
Data:22
```


# `compose()`

- It applies the first function to the output of the second function.

![[Pasted image 20240902104905 2.png]]


```java
public class ComposeExample { 
	public static void main(String[] args) { 
		// Define two functions 
		Function<Integer, Integer> multiplyBy2 = x -> x * 2; 
		Function<Integer, Integer> add3 = x -> x + 3; 
		// Compose the functions: add3 will be applied first, then multiplyBy2 
		Function<Integer, Integer> composedFunction = multiplyBy2.compose(add3); 
		// Apply the composed function to an input 
		Integer result = composedFunction.apply(5); // (5 + 3) * 2 = 16 
		System.out.println(result); // Output: 16 
	}
}
```

- In the `compose` example, the functions are executed in a right-to-left order. Firstly, `multiply` is executed and its output is passed to the `add` function. Then, the resulting output of the `add` function is passed to `logOutput` for logging purposes.



# apply()

- the `apply()` method takes and input and returns and output
- It is used to apply a function to an argument and compute a result.It is the single abstract method of these interfaces, which is required for them to be used as functional interfaces.


# Functional Currying

-  involves decomposing a function that takes multiple arguments into a sequence of functions, each of which accepts only one argument. This is in line with the definition of currying, which is a technique employed in Functional Programming.

```java
import java.util.function.Function;

public class Main {
    private static Function<Integer, Function<Integer, Function<Integer, Integer>>> trisum = (a) -> (b) -> (c) -> a+b+c;


    public static void main(String[] args) {
      System.out.println(trisum.apply(1).apply(2).apply(3));
      
  }
}
```