- It is the main functionality of Spring IOC(Inversion Of Control).
- The Spring-Core module is responsible for injecting dependencies through either Constructor or Setter methods.
- The design principle of Inversion of Control emphasizes keeping the Java classes independent of each other and the container frees them from object creation and maintenance.
-  These classes, managed by Spring, must adhere to the standard definition of Java-Bean.

### **Two Types of DI**

#### **1. Setter DI**
- injecting dependencies via setters.
```java
public class Demo{
	private String name;

	@Autowired
	public void setName(String name){
		this.name = name;
	}
}
```

#### **2. Constructor DI**
- injecting dependencies via constructors.
```java
public class Demo{
	private String name;

	public void Demo(String name){
		this.name = name;
	}
}
```


| Setter DI                                                                                                                                               | Constructor DI                                                                                                                       |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| Poor readability as it adds a lot of boiler plate codes in the application.                                                                             | Good readability as it is separately present in the code.                                                                            |
| The bean must include getter and setter methods for the properties.                                                                                     | The bean class must declare a matching constructor with arguments. Otherwise, `BeanCreationException` will be thrown.                |
| Requires addition of `@Autowired` annotation, above the setter in the code and hence, it increases the coupling between the class and the DI container. | Best in the case of loose coupling with the DI container as it is not even required to add @Autowired annotation in the code.        |
| Circular dependencies result with Setter DI because object creation happens before the injections.                                                      | No scope for circular or partial dependency because dependencies are resolved before object creation itself.                         |
| Preferred option when properties are less and mutable objects can be created.                                                                           | Preferred option when properties on the bean are more and immutable objects (eg: financial processes) are important for application. |
- [[Circular Dependencies]]