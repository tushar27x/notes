The Java Persistence API (JPA) is the Java API specification that bridges the gap between relational databases and object-oriented programming by handling the mapping of the Java objects to the database tables and vice-versa.

## **Terminologies**

#### 1. Entity
- An entity is the lightweight and persistent domain object. It represents the table in the database and each entity instance corresponds to the row in that table.
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


#### 2. Entity Manager
- An interface that is used to interact with the persistence context. 
- It is important for all database interactions in a JPA managed application.


#### 3. Persistence context
- The persistence context is the set of the entity instances in which for any persistent entity identity, there is the unique entity instance.
- This context can helps manage the entity states like managed, detached and it can ensures that the data is synchronized with the database at the end of the transaction of the application.

#### 4. JPQL
- JPQL is the query language defined as the part of the JPA specification for the making queries against the entities stored in the database of JPA application.
-  JPQL can be designed to abstract database tables as the Java classes in the queries. Making it database agnostic and more integrated with the object oriented approach of the Java.