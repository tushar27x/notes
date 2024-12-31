![[Screenshot 2024-09-19 at 2.05.29 PM.png]]

### **Presentation Layer** 

The presentation layer handles the HTTP requests, translates the JSON parameter to object, and authenticates the request and transfer it to the business layer. In short, it consists of views i.e., frontend part.

### **Business Layer**

The business layer handles all the business logic. It consists of service classes and uses services provided by data access layers. It also performs authorization and validation.

### **Persistence Layer**

The persistence layer contains all the storage logic and translates business objects from and to database rows.

### **Database Layer** 

In the database layer, CRUD (create, retrieve, update, delete) operations are performed.