
```java
// ./src/main/java/org.example/App.java
package org.example;  
  
import org.springframework.context.ApplicationContext;  
import org.springframework.context.support.ClassPathXmlApplicationContext;  
  
public class App   
{  
    public static void main( String[] args ) {  
        ApplicationContext context = new ClassPathXmlApplicationContext("spring.xml");  
        Dev obj = (Dev) context.getBean("dev");  
        obj.build();  
    }  
}
```

```java
// ./src/main/java/org.example/Dev.java
package org.example;  
  
public class Dev {  
    private Laptop laptop;  
  
    public Dev() {}  
  
    public Laptop getLaptop() {  
        return laptop;  
    }  
  
    public void setLaptop(Laptop laptop) {  
        this.laptop = laptop;  
    }  
  
  
    public void build(){  
        System.out.println("Working on a spring project");  
        laptop.compile();  
    }  
}
```

```java
// ./src/main/java/org.example/Laptop.java
package org.example;  
  
public class Laptop {  
    public void compile(){  
        System.out.println("Compiling code");  
    }  
}
```


# Setter injection


```xml
%% /src/main/resources/spring.xml%%
<beans xmlns="http://www.springframework.org/schema/beans"  
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
       xsi:schemaLocation="  
        http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">  
  
    <bean id="dev" class="org.example.Dev">  
        <property name="laptop" ref="lap" />  
    </bean>    
    
    <bean id="lap" class="org.example.Laptop">  
    </bean>
</beans>
```

# Constructor injection

```xml
%% /src/main/resources/spring.xml%%
<beans xmlns="http://www.springframework.org/schema/beans"  
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
       xsi:schemaLocation="  
        http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">  
  
    <bean id="dev" class="org.example.Dev">  
        <constructor-arg ref="lap" />  
    </bean>    
    
    <bean id="lap" class="org.example.Laptop">  
    </bean>
</beans>
```


# Autowiring

```java
package org.example;  
  
public interface Computer {  
    void compile();  
}
```

```java
package org.example;  
  
public class Dev {  
    private Computer com;  
  
    public Dev() {}  
  
    public Computer getCom() {  
        return com;  
    }  
  
    public void setCom(Computer com) {  
        this.com = com;  
    }  
  
    public void build(){  
        System.out.println("Working on a spring project");  
        com.compile();  
    }  
}
```

```xml
<beans xmlns="http://www.springframework.org/schema/beans"  
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
       xsi:schemaLocation="  
        http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">  
  
    <bean id="dev" class="org.example.Dev" autowire="byType">  
    </bean>  
    
    <bean id="com" class="org.example.Laptop" primary="true">  
    </bean>  
    
    <bean id="com1" class="org.example.Desktop">  
    </bean>
</beans>
```

[[Spring Architecture]]
[[Spring boot]]
[[REST API]]
[[Hibernate JPA]]
[[Data Injection]]
