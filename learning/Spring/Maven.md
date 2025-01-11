- It is a build automation tool.
- Utilizes Project Object Model (POM) to manage dependencies.
- We can mange all the dependencies in a Java project by adding or removing them from the `pom.xml` file which is created by maven.
```xml
<?xml version="1.0" encoding="UTF-8"?>  
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">  
    <modelVersion>4.0.0</modelVersion>  
    <parent>       
	    <groupId>org.springframework.boot</groupId>  
	    <artifactId>spring-boot-starter-parent</artifactId>  
	    <version>3.4.1</version>  
	    <relativePath/> <!-- lookup parent from repository -->  
    </parent>  
    <groupId>com.CRUDApp</groupId>  
    <artifactId>demo</artifactId>  
    <version>0.0.1-SNAPSHOT</version>  
    <name>demo</name>  
    <description>CRUD application using Spring boot</description>  
    <url/>    
    <licenses> <license/> </licenses>    
	<developers>  <developer/>    </developers>    
	<scm>       
		<connection/>       
		<developerConnection/>       
		<tag/>       
		<url/>    
	</scm>    
	<properties>       
		<java.version>17</java.version>  
	</properties>    
	<dependencies>       
		<dependency>          
			<groupId>org.springframework.boot</groupId>  
	        <artifactId>spring-boot-starter-data-jpa</artifactId>  
       </dependency>       
       <dependency>         
		    <groupId>org.springframework.boot</groupId>  
	        <artifactId>spring-boot-starter-web</artifactId>  
       </dependency>  
       <dependency>          
		    <groupId>org.postgresql</groupId>  
	        <artifactId>postgresql</artifactId>  
	        <scope>runtime</scope>  
       </dependency>       
       <dependency>          
		    <groupId>org.springframework.boot</groupId>  
		    <artifactId>spring-boot-starter-test</artifactId>  
			<scope>test</scope>  
       </dependency>    
    </dependencies>  
	<build>       
		<plugins>          
			<plugin>      
				<groupId>org.springframework.boot</groupId>  
				<artifactId>spring-boot-maven-plugin</artifactId>  
			</plugin>       
		</plugins>    
	</build>  
</project>
```



### **GAV**
- **GAV** stands for **GroupId, ArtifactId, and Version**. These three elements are used to uniquely identify a dependency or a project in the Maven repository.
#### 1. **GroupId**
- The `GroupId` is a unique identifier for a project or a group of related projects. It is usually structured in reverse domain name notation (e.g., `com.example`, `org.apache`).
- The `GroupId` typically represents the organization or the project group.
### 2. **ArtifactId**
- The `ArtifactId` is a unique identifier for the artifact (a library, framework, or project) within the specified group.
- It is typically the name of the library or module (e.g., `spring-boot-starter`, `log4j`, `my-app`).
### 3. **Version**
- The `Version` specifies the version of the artifact.
- This allows Maven to track different versions of the same library. Versions could be something like `1.0.0`, `2.5.3`, or a snapshot version like `1.0.0-SNAPSHOT`.


### **Types of Maven Repos**

#### 1. Local
- Maven local repo refers to a directory on your computer. A local repo is generated when you run any maven command for the first time.
- If the version stated in the dependent portion of the pom.xml file already exists in the local Maven repository, it is used directly. Otherwise, Maven will download a newer version.

### 2. Central
- The Apache Maven community creates the Maven central repo. It includes a large number of regularly used libraries. Maven searches in this central repo by default for any dependencies that are required but are not found in your local repo.

### 3. Remote
- We may need to set up a Maven repository within a company or project development team to host our own libraries. The company manages the Maven remote repo, which is located outside the developer's workstation.


### **Searching Dependencies**
- It searches the local repos for any set of dependencies. If it is discovered, the execution proceeds. It searches the central repo if the configured dependencies cannot be located in the local repo.  
     
- If the required dependencies are identified in the central repo, they are downloaded to the local repo for future use and reference. If no matches are discovered, Maven begins scanning the remote repos.  
     
- If no remote repo is configured, maven will throw an exception stating that it could not locate the dependencies and will stop processing. If any dependencies are discovered, they are downloaded to the local repo for future reference and use.