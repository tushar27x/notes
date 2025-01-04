- Spring boot annotations are a form of metadata that provides information about the application
- Annotations are used to provide supplemental information about the program.

### **Core Spring annotations**

- `@Required`:It applies to the **bean** setter method. It indicates that the annotated bean must be populated at configuration time with the required property, else it throws an exception **`BeanInitilizationException`**.
```java
public class Machine   
{  
	private Integer cost;  
	
	@Required  
	public void setCost(Integer cost)   {  
		this.cost = cost;  
	}  
	public Integer getCost(){  
		return cost;  
	}     
}
```

- `@Autowired`:
  An autowired application requires fewer lines of code comparatively but at the same time, it provides very little flexibility to the programmer.
  In spring the `@Autowired` annotation uses Constructor Injection.
```java
public class Machine   
{  
	private Integer cost;  
	
	@Autowired
	public void setCost(Integer cost)   {  
		this.cost = cost;  
	}  
	public Integer getCost(){  
		return cost;  
	}     
}
```

- `@Component`:
  It is a class-level annotation. It is used to mark a Java class as a bean. A Java class annotated with `@Component` is found during the classpath. The Spring Framework pick it up and configure it in the application context as a **Spring Bean**.
```java
@Component  
public class Student  
{  
.......  
}
```

- `@Controller`:
  The `@Controller`is a class-level annotation. It is a specialization of `@Component`. It marks a class as a web request handler. It is often used to serve web pages. By default, it returns a string that indicates which route to redirect. It is mostly used with `@RequestMapping` annotation.
```java
@Contoller
@RequestMapping("books")
public class BooksController{
	@RequestMapping(value = "/{name}", method = RequestMethod.GET)
	public Employee getBooksByName(){ 
		return booksTemplate;
	}
}
```


- `@SpringBootApplication:` It is a combination of three annotations `@EnableAutoConfiguration`, `@ComponentScan`, and `@Configuration`.
	  - `@EnableAutoConfiguration:` It auto-configures the bean that is present in the classpath and configures it to run the methods. The use of this annotation is reduced in Spring Boot 1.2.0 release because developers provided an alternative of the annotation, i.e. `@SpringBootApplication`.
	- `@ComponentScan:` It is used when we want to scan a package for beans. It is used with the annotation `@Configuration`. We can also specify the base packages to scan for Spring Components.
	- `@Configuration`: It is a class-level annotation. The class annotated with @Configuration used by Spring Containers as a source of bean definitions.

- `@RequestMapping`:
  It is used to map the **web requests**. It has many optional elements like **consumes, header, method, name, params, path, produces**, and **value**. We use it with the class as well as the method.
  
- `@GetMapping:` It maps the **HTTP GET** requests on the specific handler method. It is used to create a web service endpoint that **fetches** It is used instead of using: `@RequestMapping(method = RequestMethod.GET)`
- `@PostMapping:` It maps the **HTTP POST** requests on the specific handler method. It is used to create a web service endpoint that **creates** It is used instead of using: `@RequestMapping(method = RequestMethod.POST`)
- `@PutMapping`: It maps the **HTTP PUT** requests on the specific handler method. It is used to create a web service endpoint that **creates** or **updates** It is used instead of using: `@RequestMapping(method = RequestMethod.PUT)`
- `@DeleteMapping`: It maps the **HTTP DELETE** requests on the specific handler method. It is used to create a web service endpoint that **deletes** a resource. It is used instead of using: `@RequestMapping(method = RequestMethod.DELETE)`
- `@PatchMapping`: It maps the **HTTP PATCH** requests on the specific handler method. It is used instead of using: `@RequestMapping(method = RequestMethod.PATCH)`
- `@RequestBody`: It is used to **bind** HTTP request with an object in a method parameter. Internally it uses **`HTTP MessageConverters`** to convert the body of the request. When we annotate a method parameter with **@RequestBody,** the Spring framework binds the incoming HTTP request body to that parameter.
- `@ResponseBody`: It binds the method return value to the response body. It tells the Spring Boot Framework to serialize a return an object into JSON and XML format.
- `@PathVariable`: It is used to extract the values from the URI. It is most suitable for the RESTful web service, where the URL contains a path variable. We can define multiple `@PathVariable` in a method.
- `@RequestParam`: It is used to extract the query parameters form the URL. It is also known as a **query parameter**. It is most suitable for web applications. It can specify default values if the query parameter is not present in the URL.
- `@RequestHeader`: It is used to get the details about the HTTP request headers. We use this annotation as a **method parameter**. The optional elements of the annotation are **name, required, value, defaultValue.** For each detail in the header, we should specify separate annotations. We can use it multiple time in a method
- `@RestController`: It can be considered as a combination of **@Controller** and **`@ResponseBody`** annotations**.** The `@RestController` annotation is itself annotated with the `@ResponseBody` annotation. It eliminates the need for annotating each method with `@ResponseBody`.
- `@RequestAttribute`: It binds a method parameter to request attribute. It provides convenient access to the request attributes from a controller method. With the help of @RequestAttribute annotation, we can access objects that are populated on the server-side.