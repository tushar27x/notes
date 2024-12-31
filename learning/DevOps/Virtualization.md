-  We use VMware to run multiple OS.
- virtualisation is partitioning of one machine into isolated environments.
- Each virtual machine requires its own OS
![[Virtualization.png]]


**Host OS**  -> this is the operating system' of the physical machine.

**Guest OS** -> This is the operating system of the virtual machine.

**Snapshot** -> is a way of taking backup of the virtual machines.

**Hypervisor** -> a tool or software that allows us to create virtual machines.
There are two types of hypervisors:
1. *Type1 or Bare metal* - which run directly on the physical machine. It is only used for production and it won't let you use the computer for any other purpose. example -  VMware ESXi or Zen Hypervisor.
   
2. *Type2* - It runs as a software on a computer. This is just for learning and testing purpose, because obviously you're not going to run production machines on your laptop. example - VM VirtualBox

