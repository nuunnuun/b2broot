*This project has been created as part of the 42 curriculum by kraksana.*

# Born2beRoot

## Description

This project is about learning the basics of system administration using a virtual machine. The main goal is to install and configure a Linux operating system while following strict security and configuration rules. Through this project, I learn how an operating system works, how to manage users, services, and security policies, and how to use virtualization tools.

## Instructions

### Installation

1. Install a virtualization software which is already given on 42 computer (VirtualBox).
2. Download the ISO file of the chosen operating system (Debian).
3. Create a new virtual machine with the required resources.
4. Boot the virtual machine using the ISO file and follow the installation steps.

### Execution

* Log in using the created user account.
* Ensure SSH is running on the required port.
* Check that the firewall is enabled and configured correctly.
* Verify password policies, sudo rules, and monitoring scripts.

## Resources

* Debian Documentation
Used to study system installation, user and group management, package management with APT, networking, SSH configuration, and security mechanisms such as AppArmor.
* Rocky Linux Official Documentation
Consulted for comparison purposes, particularly regarding enterprise Linux features, SELinux, and differences in system administration approaches compared to Debian.
* 42 Born2beRoot Subject PDF
Served as the primary specification for project requirements, constraints, mandatory configurations, and evaluation criteria.
* Linux Manual Pages (man)
Used extensively to understand the behavior, options, and correct usage of system commands such as useradd, usermod, passwd, sudo, ufw, cron, ssh, lsblk, df, and free.
* Born2beRoot guidebook 
Used as a supplementary learning reference to better understand the project workflow, common configuration steps, and typical pitfalls encountered during system setup.

### AI Usage

Artificial Intelligence tools were used strictly as a learning aid during the development of this project. 

AI assistance was utilized for the following purposes:
- Clarifying all Linux concepts (e.g., virtual machines, LVM, firewall behavior, SSH, and user permissions)
- Explaining command syntax and system behavior using official documentation and manual pages as references
- Helping structure explanations and documentation in a clear and organized manner

## Project Description

### Operating System Choice

#### Debian

**Advantages:**
- High stability, making it suitable for long-running systems
- Extensive community support and comprehensive documentation
- Simple and clear configuration process, ideal for learning Linux system administration

**Limitations:**
- Software packages are not always the most recent versions
- Less focused on enterprise-specific environments compared to RHEL-based systems

#### Rocky Linux

**Advantages:**
- Enterprise-grade stability and reliability
- Fully compatible with Enterprise Linux
- Strong security enforcement through SELinux

**Limitations:**
- More complex configuration
- Smaller community and fewer beginner-oriented resources than Debian

**Chosen Operating System:** **Debian**  
Debian was selected for this project because of its stability, simplicity, and extensive documentation, allowing a stronger focus on core Linux concepts required by the project.


### Design Choices

#### Partitioning

* LVM with encrypted partitions
* Separate partitions for system and user data

#### Security Policies

* Strong password rules
* Password expiration enabled
* Limited sudo access

#### User Management

* One main user
* Dedicated sudo group

#### Services Installed

* OpenSSH
* Firewall
* Monitoring script

## Comparisons

### Debian vs Rocky Linux

I chose to use  Debian because it is lightweight, extremely stable, well-documented, easier to configure for learning Linux fundamentals, and fully compatible with all Born2beRoot requirements, while being simpler to manage than Rocky Linux.

### AppArmor vs SELinux

AppArmor is easier to configure and understand, while SELinux provides stronger and more detailed access control but is more complex.

### UFW vs firewalld

UFW is simple and user-friendly, while firewalld is more flexible and powerful, especially for servers.

### VirtualBox vs UTM

VirtualBox is widely used and beginner-friendly, while UTM is better optimized for Apple Silicon devices.
