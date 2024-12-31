# Linux

### Principles

- Everything is a file (including hardware).
- Small single purpose programs.
- Ability to chain programs together for complex operations.
- Avoid captive user interface, i.e. avoid GUI.
- configuration data stored in text files, which means that we can easily make changes to files, we don't need navigate through the GUI for making changes to the software.


### Why Linux?

- Opensource
- Community Support
- Support wide variety of hardware.
- Customization.
- Most servers run on Linux.
-  Automation
- Security


### Architecture

![[linux.jpg]]

- Hardware - compute resources such as RAM, CPU etc.
- Kerner - reads and understand Hardware and can pass signal to and through to your hardware to shell.
- Shell - you can execute commands and expect a return. 


### RPM v/s Debian

In the land of Linux, there are two main package managers: RPM and DEB. RPM is used by Red Hat-based distributions such as Fedora and CentOS, while DEB is used by Debian-based distributions such as Ubuntu and Linux Mint.

 - RPM - RHEL (Red Hat Enterprise Linux), CentOS, Fedora etc.
 - Debian -  Ubuntu, Linux Mint, Kali etc.

Both RPM and DEB are used to install, update, and remove software packages on Linux computers. They do this by storing all the files and information needed to install a piece of software in a package file. When a user installs a package, the package manager takes care of everything for them, including downloading the package, extracting the files, and configuring the software.

One difference between RPM and DEB is the tools they use to manage packages. RPM uses tools such as `yum` or `zypper`, while DEB uses tools such as apt-get or aptitude. These tools provide an easy-to-use interface for managing packages.

- Red Hat is considered as stable and secure operating system, especially Red Hat Enterprise Linux.
- You cannot download and install software in RHEL Linux from outside. You download it only from Red Hat repository. 
- Red Hat is going to test all the software and packages before it releases it to its users, like same like Apple
- Which will test the software very thoroughly for any security or for any performance flaw.
- In Debian-based. Here, you get lots and lots of software very easily, very easy to install, very easy to set up. It focuses more on user friendliness. 
- So if you need latest and greatest in open source software, you go with Debian-based like Ubuntu.

**So for running servers choose RPM and for DevOps where you might require latest and greatest libraries choose Debian**

![[Pasted image 20240720122033.png]]

