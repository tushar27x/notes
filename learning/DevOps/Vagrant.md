# Vagrant

- It is a tool that is used to create virtual machines automatically.
- It manages the lifecycle of VMs right from creating, making changes, and cleaning up.
- It is not a replacement of hypervisors(such as Oracle Virtual  Box); It's built on top of hypervisors.

### Need for automation tools

- Tools like vagrant are used to avoid human errors while setting up VMs and installing OS.
- Setting up VMs is a time consuming process.


### Features

- In vagrant there is no OS installation required using ISO files.
- It uses VM images ( or Box).
- These images are ready-made virtual machines stored on Vagrant cloud.
- These images are freely available which vagrant will download and store them in your local computer.
- This allows us to create as many VMs as we want, as many times as we want.
- All the VM configurations are stored in a `VagrantFile` and we can make changes to the CPU, RAM, IP address by editing this file.

### Architecture

![[Pasted image 20240718115623.png]]

- First we create a vagrant file.
- After that we run the command
```bash
vagrant up
```


- Vagrant is going to read the `Vagrantfile`, and see if the box, which is the image, is available in your local machine. 
- If it's not available in your local machine, it will go to Vagrant Cloud, download the image, and then it is gonna contact the hypervisor, which in our case is Oracle VM VirtualBox, and that's the default hypervisor. 
- The default hypervisor is Oracle VirtualBox.
- It will contact the Oracle VirtualBox, and give the information of creating the VM, and then the VM will get created. 
- You can create one or many VM by using Vagrant. 
- The simple to use Vagrant commands like 
	- `vagrant halt` - power off VM
	- `vagrant reload` - reboot VM
	- `vagrant destroy` - delete VM
- and when you reload, it's gonna read the `Vagrantfile` when it's coming up. 
- So any changes will be applied. 
- If you were to log into a Linux VM, you can do `vagrant ssh`, and like that, there are many more commands. 

### Steps to create a VM using vagrant

There are very simple steps to create virtual machine with vagrant. 
- First you need to create a folder in your computer. 
- Then you place a `Vagrantfile` in that folder, you issue the command vagrant up,
- and then you can use `vagrant ssh` to log into the VM, and you can use later `vagrant halt` to power off, or `vagrant destroy` to delete the VM.


To list all the vagrant boxes in your machine use command `vagrant box list`
