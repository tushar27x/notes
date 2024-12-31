
# 1. Constructor Injection

```java
public interface Coach {  
    String getTraining();  
}
```

```java
@Component  
public class CricketCoach implements Coach{  
    @Override  
    public String getTraining(){  
        return "Practice bowling for 15 minutes";  
    }  
}
```

```java
@RestController  
public class DemoContoller {  
    private Coach myCoach;  
  
    @Autowired  
	public DemoContoller(Coach coach){  
	    myCoach = coach;  
	}  
  
    @GetMapping("/get-training")  
    public String getMessage(){  
        return myCoach.getTraining();  
    }  
}
```



# 2. Setter Injection

```java
@RestController  
public class DemoContoller {  
    private Coach myCoach;  
  
    @Autowired  
    public void setCoach(CricketCoach coach){  
        myCoach = coach;  
    }  
  
    @GetMapping("/get-training")  
    public String getMessage(){  
        return myCoach.getTraining();  
    }  
}
```


# 3. Field Injection (Not Recommended)

- makes code harder to unit test.
```java
@RestController  
public class DemoContoller {  
    @Autowired  
    private Coach myCoach;      
  
    @GetMapping("/get-training")  
    public String getMessage(){  
        return myCoach.getTraining();  
    }  
}
```

# Qualifiers

- When we have multiple implementations of the same interface we need to use Qualifiers to tell Spring which implementation to use

```java
@RestController  
public class DemoContoller {  
    private Coach myCoach;  
  
    @Autowired  
    public DemoContoller(@Qualifier("baseballCoach") Coach coach){  
        myCoach = coach;  
    }  
  
    @GetMapping("/get-training")  
    public String getMessage(){  
        return myCoach.getTraining();  
    }  
}
```


# Primary

- when we have to set a default implementation.
- you can't have multiple primary implementation.
- `@Qualifier` has a higher priority that `@Primary`.
```java
@Component  
@Primary  
public class CricketCoach implements Coach{  
    @Override  
    public String getTraining(){  
        return "Practice bowling for 15 minutes :-)";  
    }  
}
```

# Lazy Initialization

- We can specify which bean need to be created at the time of initialization and which needs to be created at the time of request by using `@Lazy`.

```java
@Component  
@Lazy  
public class CricketCoach implements Coach{  
    @Override  
    public String getTraining(){  
        return "Practice bowling for 15 minutes :-)";  
    }  
}
```

- We can make sure that all the beans are lazily created by adding the following statement in the `application.properties file`.

```
spring.application.lazy-initialization=true
```

# Bean Scopes

Scope refers to 
- the lifecycle of the bean.
- How is it shared
- how many instances are created.
- how the bean is shared
- The default scope is `SINGLETON`, 
- If you set the scope to `PROTOTYPE` then a new instance will be created for every new request to the container

```java
@Component  
@Scope(ConfigurableBeanFactory.SCOPE_PROTOTYPE)  
public class CricketCoach implements Coach{  
    public CricketCoach(){  
        System.out.println("In constructor: "+ getClass().getName());  
    }  
    @Override  
    public String getTraining(){  
        return "Practice bowling for 15 minutes :-)";  
    }  
}
```

# Bean lifecycle methods

- these methods help us to implement our own logic
- such as calling custom business logic
- setting up handles to resources etc.
```java
@Component   
public class CricketCoach implements Coach{  
    public CricketCoach(){  
        System.out.println("In constructor: "+ getClass().getName());  
    }  
  
    @PostConstruct  
    public void doStartupStuff(){  
        System.out.println("In doStartupStuff: "+getClass().getName());  
    }  
    @PreDestroy  
    public void doDestroyStuff(){  
        System.out.println("In doDestroyStuff: "+getClass().getName());  
    }  
  
    @Override  
    public String getTraining(){  
        return "Practice bowling for 15 minutes :-)";  
    }  
}
```


💡 **For "prototype" scoped beans, Spring does not call the destroy method. Gasp!**  

In contrast to the other scopes, Spring does not manage the complete lifecycle of a prototype bean: the container instantiates, configures, and otherwise assembles a prototype object, and hands it to the client, with no further record of that prototype instance.

Thus, although initialization lifecycle callback methods are called on all objects regardless of scope,_ in the case of prototypes, configured destruction lifecycle callbacks are not called. The client code must clean up prototype-scoped objects and release expensive resources that the prototype bean(s) are holding.


# Bean annotation

- we can create instance of a class by using the `@Bean` annotation instead of the the `@Component` annotation
- We do this to incorporate _third-party_ classes available as a Spring framework.
- 