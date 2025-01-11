
### **Making Entity**

```java
package com.CRUDApp.demo.models;  
  
import jakarta.persistence.Entity;  
import jakarta.persistence.GeneratedValue;  
import jakarta.persistence.GenerationType;  
import jakarta.persistence.Id;  
  
@Entity  
public class User {  
    @Id  
    @GeneratedValue(strategy = GenerationType.IDENTITY)  
    private Long id;  
    private String username;  
    private String email;  
  
}
```
*Annotations used*
- `@Entiity`: Marks the class as [[JPA]] entity. It means this class will be mapped to a table in the database.
- `@Id`: Marks the primary key of the table.
- `@GeneratedValue`: Specifies how the primary key (`id`) value will be generated.
- `GenerationType.IDENTITY` strategy means the database will handle the generation of the primary key value, typically using an auto-increment mechanism.
  Other strategies for `@GeneratedValue` include:
	- `AUTO`: JPA automatically selects the strategy based on the underlying database.
	- `SEQUENCE`: Uses a database sequence to generate primary key values.
	- `TABLE`: Uses a separate table to generate primary key values.


### **Making Repository**
```java
package com.CRUDApp.demo.repository;  
  
import com.CRUDApp.demo.entity.User;  
import org.springframework.data.jpa.repository.JpaRepository;  
import org.springframework.stereotype.Repository;  
  
@Repository  
public interface UserRepository extends JpaRepository<User, Long> {  
}
```

*Annotations used*:
- `@Repository`: this annotation marks the interface as a repository in spring framework.
  Spring Data JPA automatically detects this annotation (though it is optional since `JpaRepository` is already a repository).
  
- `public interface UserRepository`: Declares `UserRepository` as an interface.

- `extends JpaRepository<User, Long>`: Extends the `JpaRepository` interface provided by Spring Data JPA. The two parameters, `<User, Long>`, specify:
	`User`: The entity class this repository manages.
	`Long`: The type of the primary key (ID) of the `User` entity.

By extending `JpaRepository`, `UserRepository` automatically inherits several methods for managing `User` entities, including:

- **CRUD Operations**:
    - `save(S entity)`: Save or update an entity.
    - `findById(ID id)`: Find an entity by its primary key.
    - `findAll()`: Retrieve all entities.
    - `deleteById(ID id)`: Delete an entity by its primary key.
- **Pagination and Sorting**:
    - `findAll(Sort sort)`: Retrieve all entities with sorting.
    - `findAll(Pageable pageable)`: Retrieve paginated data.
- **Custom Queries**:
    - You can define additional methods (e.g., `findByEmail(String email)`) for specific queries.


### **Making Controller**
```java
package com.CRUDApp.demo.controllers;  
  
import com.CRUDApp.demo.entity.User;  
import com.CRUDApp.demo.repository.UserRepository;  
import org.springframework.web.bind.annotation.*;  
  
import java.util.List;  
import java.util.Optional;  
  
@RestController  
@RequestMapping("/users")  
public class UserController {  
    private final UserRepository userRepository;  
  
  
    public UserController(UserRepository userRepository) {  
        this.userRepository = userRepository;  
    }  
  
    @GetMapping("/{id}")  
    public Optional<User> findUserById(@PathVariable Long id){  
        return userRepository.findById(id);  
    }  
  
    @GetMapping  
    public List<User> find(){  
        return userRepository.findAll();  
    }  
  
    @PostMapping  
    public void createUser(@RequestBody User user){  
        userRepository.save(user);  
    }  
  
    @PutMapping("/{id}")  
    public void updateUser(@PathVariable Long id, @RequestBody User user){  
        user.setId(id);  
        userRepository.save(user);  
    }  
  
    @DeleteMapping("/{id}")  
    public void deleteUser(@PathVariable Long id){  
        userRepository.deleteById(id);  
    }  
}
```

*Annotations Used*
- `@GetMapping` => get requests
- `@PutMapping` => put  requests
- `@PostMapping` => post  requests
- `@DeleteMapping` => Delete requests
- `@PathVariable` => access URL parameter variables
- `@RequestBody` => access variables passed through URL body

### **Making DB connections**

```java
spring.application.name=demo  
spring.datasource.url=jdbc:postgresql://ep-floral-leaf-a57q5x84.us-east-2.aws.neon.tech/neondb?sslmode=require  
spring.datasource.username=<username> 
spring.datasource.password=<password> 
spring.jpa.hibernate.ddl-auto=update
```

