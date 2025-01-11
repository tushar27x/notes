<article>
Inversion of Control (IOC) is a design principle where the control of objects creation and management of their dependencies is transferred from the application code to a container or framework.
</article>

- **Control Reversal**: In traditional programming the application code is responsible for handling creation and managing of objects. However, in IoC, the responsibility of managing objects is transferred to a container or framework, which decides when and how the objects should be created and injected into the application.
- **DI**: Instead of objects creating their dependencies, they receive the dependencies from an external source, typically a container.
  In Spring, the IoC container manages the creation, configuration, and assembly of beans (objects) and their dependencies. Spring achieves this through **DI** (using constructor injection, setter injection, or field injection).



💡**The IoC container stores classes marked with `@Component` annotation**

