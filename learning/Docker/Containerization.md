- Containerization is a software deployment process that bundles an application’s code with all the files and libraries it needs to run on any infrastructure.
- with the help of containerization we can create all a single version of a software that will run on all machines and environments

### **Containers and Images**
- a container is another process on your machine that has been isolated from all other processes on the host machine.
- **Container Image** -  a container image is an executable packages that include everything to run a piece of software including :
	- code
	- dependencies
	- configurations
- ***Characteristics***:
	- Immutable
	- Portable
	- Layered structure: Built in layers, where each layer represents a specific instruction (e.g., adding a file, installing a dependency). This structure makes them efficient, as layers can be reused across different images.

### **Benefits**
- **Portability** - deploy applications in multiple environments without rewriting the program code.
- **Scalability**-  Containers are lightweight software components that run efficiently. a virtual machine can launch a containerized application faster because it doesn't need to boot an operating system.
- **Agility** - Containerized applications run in isolated computing environments. Software developers can troubleshoot and change the application code without interfering with the operating system, hardware, or other application services