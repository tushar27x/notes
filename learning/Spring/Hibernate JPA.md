## Making a connection to MySQL database

```
spring.datasource.url=jdbc:mysql://localhost:3306/student_tracker  
spring.datasource.username=springstudent  
spring.datasource.password=springstudent
```


## Main application

```java
import org.springframework.boot.CommandLineRunner;  
import org.springframework.boot.SpringApplication;  
import org.springframework.boot.autoconfigure.SpringBootApplication;  
import org.springframework.context.annotation.Bean;  
  
@SpringBootApplication  
public class CrudDemoApplication {  
  
    public static void main(String[] args) {  
       SpringApplication.run(CrudDemoApplication.class, args);  
    }  
  
    @Bean  
    public CommandLineRunner commandLineRunner(String [] args){  
       return runner->{  
          System.out.println("Hello world");  
       };  
    }  
}
```

## Mapping Student table to Student class

```java
package com.tushar.CrudDemo.entity;  
  
import jakarta.persistence.*;  

@Entity
@Table(name = "student")  
public class Student {  
    @Id  
    @Column(name = "id")  
    @GeneratedValue(strategy = GenerationType.IDENTITY)  
    private String id;  
  
    @Column(name = "first_name")  
    private String firstName;  
  
    @Column(name = "last_name")  
    private String lastName;  
  
    @Column(name = "email")  
    private String email;  
  
//    no arg constructor  
    public Student(){}  
  
//    arg constructor  
    public Student(String fName, String lName, String mail){  
        this.firstName = fName;  
        this.lastName = lName;  
        this.email = mail;  
    }  
  
    public String getId() {  
        return id;  
    }  
  
    public void setId(String id) {  
        this.id = id;  
    }  
  
    public String getFirstName() {  
        return firstName;  
    }  
  
    public void setFirstName(String firstName) {  
        this.firstName = firstName;  
    }  
  
    public String getLastName() {  
        return lastName;  
    }  
  
    public void setLastName(String lastName) {  
        this.lastName = lastName;  
    }  
  
    public String getEmail() {  
        return email;  
    }  
  
    public void setEmail(String email) {  
        this.email = email;  
    }  
  
    @Override  
    public String toString() {  
        return "Student{" +  
                "id='" + id + '\'' +  
                ", firstName='" + firstName + '\'' +  
                ", lastName='" + lastName + '\'' +  
                ", email='" + email + '\'' +  
                '}';  
    }  
}
```

## CRUD

**main.java**
```java
package com.example.crudApp;  
  
import com.example.crudApp.dao.StudentDAO;  
import com.example.crudApp.entity.Student;  
import org.springframework.boot.CommandLineRunner;  
import org.springframework.boot.SpringApplication;  
import org.springframework.boot.autoconfigure.SpringBootApplication;  
import org.springframework.context.annotation.Bean;  
  
import java.util.List;  
  
import static org.hibernate.internal.util.collections.ArrayHelper.forEach;  
  
@SpringBootApplication  
public class CrudAppApplication {  
  
    public static void main(String[] args) {  
       SpringApplication.run(CrudAppApplication.class, args);  
    }  
  
    @Bean  
    public CommandLineRunner commandLineRunner(StudentDAO studentDAO){  
       return runner ->{  
//        createStudent(studentDAO);  
//        findById(studentDAO,2);  
//        findAllStudents(studentDAO);  
//        findByFirstName(studentDAO,"John");  
//        findByLastName(studentDAO,"Sharma");  
//        findByEmail(studentDAO, "example.@mail.com");  
  
//        Student updateStudent = findById(studentDAO, 2);  
//        update(studentDAO, updateStudent);  
  
//        deleteById(studentDAO, 1);  
  
          empty(studentDAO);  
       };  
    }  
  
    private void createStudent(StudentDAO studentDAO) {  
       Student tempStudent = new Student("John","Doe","example.@mail.com");  
       studentDAO.save(tempStudent);  
       System.out.println("Created student: "+tempStudent.getId());  
    }  
  
    private Student findById(StudentDAO studentDAO, Integer id){  
       Student foundStudent = studentDAO.findById(id);  
       if (foundStudent == null) {  
          System.out.println("No records found");  
          return null;  
       }  
       System.out.println(foundStudent.toString());  
       return foundStudent;  
    }  
  
    private void findAllStudents(StudentDAO studentDAO){  
       List<Student> res = studentDAO.findAll();  
       if(res.isEmpty()){  
          System.out.println("No records found");  
       }  
       for (Student student : res) {  
          System.out.println(student.toString());  
       }  
    }  
    private void findByFirstName(StudentDAO studentDAO, String fName){  
       List<Student> res = studentDAO.findByFirstName(fName);  
       if(res.isEmpty()){  
          System.out.println("No records found");  
       }  
       for(Student s : res){  
          System.out.println(s.toString());  
       }  
    }  
    private void findByLastName(StudentDAO studentDAO, String lName){  
       List<Student> res = studentDAO.findByLastName(lName);  
       if(res.isEmpty()){  
          System.out.println("No records found");  
       }  
       for(Student s : res){  
          System.out.println(s.toString());  
       }  
    }  
    private void findByEmail(StudentDAO studentDAO, String email){  
       List<Student> res = studentDAO.findByEmail(email);  
       if(res.isEmpty()){  
          System.out.println("No records found");  
       }  
       for(Student s : res){  
          System.out.println(s.toString());  
       }  
    }  
  
    private void update(StudentDAO studentDAO, Student s){  
       if(s == null){  
          System.out.println("No record found");  
          return;  
       }  
       s.setLastName("Walker");  
       s.setEmail("paul.walker@mail.com");  
       studentDAO.update(s);  
       studentDAO.findById(Integer.parseInt(s.getId()));  
    }  
    private void deleteById(StudentDAO studentDAO, Integer id){  
       Student s = studentDAO.deleteById(id);  
       if(s == null){  
          System.out.println("No data found");  
          return;  
       }  
       System.out.println("Delete student: "+s.toString());  
    }  
  
    private void empty(StudentDAO studentDAO){  
       int res = studentDAO.deleteAll();  
       System.out.println("Rows deleted: "+res);  
    }  
}
```

**StudentDAO.java**
```java
package com.example.crudApp.dao;  
  
import com.example.crudApp.entity.Student;  
  
import java.util.List;  
  
public interface StudentDAO {  
    void save(Student student);  
    Student findById(Integer id);  
    List<Student> findByFirstName(String fName);  
    List<Student> findByLastName(String lName);  
    List<Student> findByEmail(String email);  
    List<Student> findAll();  
    void update(Student s);  
    Student deleteById(Integer id);  
  
    int deleteAll();  
}
```


**StudentDAOImpl.java**
```java
package com.example.crudApp.dao;  
  
import com.example.crudApp.entity.Student;  
import jakarta.persistence.EntityManager;  
import jakarta.persistence.TypedQuery;  
import org.springframework.beans.factory.annotation.Autowired;  
import org.springframework.stereotype.Repository;  
import org.springframework.transaction.annotation.Transactional;  
  
import java.util.List;  
  
@Repository  
public class StudentDAOImpl implements StudentDAO{  
    private EntityManager entityManager;  
  
    @Autowired  
    public StudentDAOImpl(EntityManager entityManager) {  
        this.entityManager = entityManager;  
    }  
  
    @Override  
    @Transactional    public void save(Student student) {  
        entityManager.persist(student);  
    }  
  
    @Override  
    public Student findById(Integer id) {  
        return entityManager.find(Student.class,id);  
    }  
  
    @Override  
    public List<Student> findByFirstName(String fName) {  
        TypedQuery<Student> q = entityManager.createQuery("FROM Student WHERE firstName=:fname", Student.class);  
        q.setParameter("fname",fName);  
        return q.getResultList();  
    }  
    @Override  
    public List<Student> findByLastName(String lName) {  
        TypedQuery<Student> q = entityManager.createQuery("FROM Student WHERE lastName=:lname", Student.class);  
        q.setParameter("lname",lName);  
        return q.getResultList();  
    }  
  
    @Override  
    public List<Student> findByEmail(String email) {  
        TypedQuery<Student> q = entityManager.createQuery("FROM Student WHERE email=:email", Student.class);  
        q.setParameter("email",email);  
        return q.getResultList();  
    }  
  
    @Override  
    public List<Student> findAll() {  
//        the JPQL query takes the name of the entity not the name of the table  
        TypedQuery<Student> q = entityManager.createQuery("FROM Student", Student.class);  
        return q.getResultList();  
    }  
  
    @Override  
    @Transactional    public void update(Student s){  
        entityManager.merge(s);  
    }  
  
    @Override  
    @Transactional    public Student deleteById(Integer id) {  
        Student s = entityManager.find(Student.class, id);  
        entityManager.remove(s);  
        return s;  
    }  
  
    @Override  
    @Transactional    public int deleteAll() {  
        return entityManager.createQuery("DELETE FROM Student").executeUpdate();  
    }  
}
```