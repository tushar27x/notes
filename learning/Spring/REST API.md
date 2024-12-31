
- for creating `RESTfull` in spring we make use of the service, DAO architecture
- the rest controller will call the service and
- then the service will call the methods on the DAO.
- This is done to make applications scalable.

_EmployeeServiceImpl.java_
```java
package com.example.restCRUD.service;  
  
import com.example.restCRUD.DAO.EmployeeDAO;  
import com.example.restCRUD.entity.Employee;  
import org.springframework.beans.factory.annotation.Autowired;  
import org.springframework.stereotype.Service;  
import org.springframework.transaction.annotation.Transactional;  
  
import java.util.List;  
  
@Service  
public class EmployeeServiceImpl implements EmployeeService{  
    private EmployeeDAO employeeDAO;  
  
    @Autowired  
    public EmployeeServiceImpl(EmployeeDAO employeeDAO) {  
        this.employeeDAO = employeeDAO;  
    }  
  
    @Override  
    public List<Employee> findAll() {  
        return employeeDAO.findAll();  
    }  
  
    @Override  
    @Transactional    public Employee save(Employee emp) {  
        return employeeDAO.save(emp);  
    }  
  
    @Override  
    public Employee findById(int id) {  
        return employeeDAO.findById(id);  
    }  
  
    @Override  
    @Transactional    public void deleteById(int id) {  
        employeeDAO.deleteById(id);  
    }  
}
```

All the transactional data is placed on the Service side of the application


_EmployeeDAOImpl.java_
```java
package com.example.restCRUD.DAO;  
  
import com.example.restCRUD.entity.Employee;  
import jakarta.persistence.EntityManager;  
import jakarta.persistence.TypedQuery;  
import org.springframework.beans.factory.annotation.Autowired;  
import org.springframework.context.annotation.Bean;  
import org.springframework.stereotype.Repository;  
import org.springframework.transaction.annotation.Transactional;  
  
import java.util.List;  
@Repository  
public class EmployeeDAOImpl implements EmployeeDAO {  
    private EntityManager entityManager;  
  
    @Autowired  
    public EmployeeDAOImpl(EntityManager entityManager){  
        this.entityManager = entityManager;  
    }  
  
  
    @Override  
    public List<Employee> findAll() {  
        TypedQuery<Employee> q = entityManager.createQuery("FROM Employee", Employee.class);  
        return q.getResultList();  
    }  
  
    @Override  
    public Employee save(Employee emp){  
        return entityManager.merge(emp);  
    }  
  
    @Override  
    public Employee findById(int id) {  
        return entityManager.find(Employee.class, id);  
    }  
  
    @Override  
    public void deleteById(int id) {  
        Employee emp = entityManager.find(Employee.class, id);  
        entityManager.remove(emp);  
    }  
}
```

_EmployeeController.java_
```java
package com.example.restCRUD.rest;  
  
import com.example.restCRUD.DAO.EmployeeDAOImpl;  
import com.example.restCRUD.entity.Employee;  
import com.example.restCRUD.service.EmployeeService;  
import org.springframework.beans.factory.annotation.Autowired;  
import org.springframework.web.bind.annotation.*;  
  
import java.util.List;  
  
@RestController  
@RequestMapping("/api/employee")  
public class EmployeeController {  
    private final EmployeeService employeeService;  
  
    @Autowired  
    public EmployeeController(EmployeeService employeeService) {  
        this.employeeService = employeeService;  
    }  
  
    @GetMapping("/all")  
    public List<Employee> getAllEmp(EmployeeDAOImpl e){  
        return employeeService.findAll();  
    }  
  
    @GetMapping("/{employeeId}")  
    public Employee findById(@PathVariable int employeeId){  
        Employee found = employeeService.findById(employeeId);  
        if(found == null){  
            throw new RuntimeException("Employee not found");  
        }  
        return found;  
    }  
  
    @PostMapping("/add")  
    public Employee addNewEmployee(@RequestBody Employee emp){  
        emp.setId(0);  
        return employeeService.save(emp);  
    }  
  
    @PutMapping("/update")  
    public Employee updateEmployee(@RequestBody Employee updatedInfo){  
        return employeeService.save(updatedInfo);  
    }  
  
    @DeleteMapping("/delete/{empId}")  
    public String deleteEmployee(@PathVariable int empId){  
        Employee found = employeeService.findById(empId);  
        if(found == null){  
            throw new RuntimeException("Employee not found");  
        }  
        employeeService.deleteById(empId);  
        return "Delete employee with id:"+empId;  
    }  
}
```



# Better way 

- make use of JPA Repository 
```java
package com.example.restCRUD.DAO;  
@Repository  
public interface EmployeeRepository extends JpaRepository<Employee,Integer> {  
 
}
```
 this will generate all the methods such as `findAll`, `deleteById` etc. for us.


- this will also generate the controller routes for us.
- So we don't need to create the routes as well.
- Just add the dependency in the `pom.xml`
```xml
<dependency>  
    <groupId>org.springframework.boot</groupId>  
    <artifactId>spring-boot-starter-data-rest</artifactId>  
</dependency>
```

So, our routes will look like:
- GET (get all)- `http://localhost:8080/employees`
- GET  (get by id) - `http://localhost:8080/employees/{id}`
- POST - `http://localhost:8080/employees`
- POST - `http://localhost:8080/employees`
- DELETE - `http://localhost:8080/employees/{id}`