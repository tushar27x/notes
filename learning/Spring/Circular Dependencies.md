- circular dependency is a relation between two or more modules that either directly or indirectly depend on each other to function properly.

>Bean A → Bean B → Bean A

Bean A needs Bean B and Bean B needs Bean C. So here Spring will create bean C, then create bean B (and inject bean C into it), then create bean A (and inject bean B into it).
There is a bean A that depends on another bean B, and the bean B depends on bean A as well just like below.

> Bean A → Bean B → Bean A

Here as you can see, there is a circular dependency and Spring won’t be able to decide which of the beans should be created first, since they depend on one another. When Spring encountered this type of issue, it raise an exception **`BeanCurrentlyInCreationException`** while loading context.


### **Workarounds**

- `@Lazy`: 
	- By default, Spring creates all singleton beans eagerly at the startup/bootstrapping of the application context. The reason behind this is simple: to avoid and detect all possible errors immediately rather than at runtime.
	- The `@Lazy` annotation in Spring Framework is used to delay the initialization of a bean until it is explicitly requested.
	- So with the help of @Lazy annotation, we can solve the issue. We can tell Spring to initialize one of the beans lazily. The injected bean will only be fully created when it’s first needed and at the time of bean creation, it injects the proxy bean as a dependency.
- Setter Injection:
	- Instead of going for constructor-based dependency injection in the context of circular dependency, we should go for Setter-based dependency injection as suggested by Spring documentation. This way, Spring creates the beans, but the dependencies are not injected until they are needed.