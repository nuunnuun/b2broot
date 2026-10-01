*This project has been created as part of the 42 curriculum by kraksana.*

# Born2beRoot

Born2beRoot is a system administration project from the 42 curriculum focused on installing, configuring, and securing a Linux server inside a virtual machine.

The project introduces core Linux administration concepts such as virtualization, disk partitioning, user management, SSH, firewall configuration, sudo policies, password security, and system monitoring.

## Project Overview

For this project, I created a Debian virtual machine using VirtualBox and configured the system according to the Born2beRoot security requirements.

The main objectives were to:

- Install and configure a Linux operating system inside a virtual machine
- Configure encrypted disk partitions using LVM
- Create and manage users and groups
- Apply password security policies
- Configure and restrict sudo access
- Set up SSH for secure remote access
- Configure a firewall
- Enable mandatory access control using AppArmor
- Create a system monitoring script
- Automate the monitoring script using cron

## What I Learned

Through this project, I gained practical experience with Linux system administration and learned how different parts of a Linux system work together.

Key concepts covered include:

- Virtual machines and virtualization
- Linux filesystem structure
- Disk partitioning
- Logical Volume Manager (LVM)
- Encrypted partitions
- Linux users and groups
- File permissions
- Package management with APT
- SSH configuration
- Firewall rules
- sudo permissions and logging
- Password policies
- AppArmor
- cron jobs
- System monitoring
- Linux services and processes

The project also helped me become more comfortable using the Linux command line and reading manual pages and configuration files.

## System Configuration

### Operating System

The virtual machine was configured using **Debian**.

Debian was selected because it provides:

- High system stability
- Extensive documentation
- Strong community support
- Straightforward package management
- A simple environment for learning Linux system administration

### Virtualization

The system runs inside **VirtualBox**, which provides an isolated virtual environment where the operating system can be installed and configured without affecting the host machine.

### Partitioning

The system uses:

- Encrypted partitions
- Logical Volume Manager (LVM)
- Separate logical volumes for important parts of the filesystem

Using LVM makes storage management more flexible because logical volumes can be managed independently from physical disk partitions.

Encryption helps protect stored data if the virtual disk is accessed without authorization.

## Security Configuration

### User Management

The system includes:

- A non-root administrative user
- Dedicated user groups
- Restricted administrative privileges
- Controlled access to privileged commands

User and group management is performed using standard Linux tools such as:

```bash
adduser
useradd
usermod
groupadd
passwd
```

### Password Policy

Strong password rules were configured to improve account security.

The policy includes requirements related to:

- Password length
- Password complexity
- Password expiration
- Minimum time before a password can be changed
- Warning period before password expiration

These rules help reduce the risk of weak or reused passwords.

### sudo Configuration

Administrative commands are executed using `sudo` instead of logging in directly as the root user.

The sudo configuration includes restrictions and logging rules to provide better control over privileged actions.

Useful commands include:

```bash
sudo -l
sudo visudo
```

### SSH

OpenSSH was installed and configured to provide secure remote access to the virtual machine.

The SSH configuration includes restrictions such as:

- A custom SSH port
- Root login disabled
- Controlled user access

SSH status can be checked using:

```bash
systemctl status ssh
```

### Firewall

The firewall is configured using **UFW (Uncomplicated Firewall)**.

Only the required ports are allowed.

Useful commands include:

```bash
sudo ufw status
sudo ufw status numbered
```

### AppArmor

Debian uses **AppArmor** as its mandatory access control system.

AppArmor restricts applications using security profiles that define which files and system resources a program is allowed to access.

The current status can be checked using:

```bash
sudo aa-status
```

## Monitoring

A monitoring script was created to display useful system information such as:

- Operating system architecture
- CPU information
- Memory usage
- Disk usage
- CPU load
- Last system boot
- LVM status
- Active TCP connections
- Logged-in users
- Network information
- Number of sudo commands executed

The script is automatically executed using `cron`.

Cron allows commands or scripts to run automatically at scheduled intervals.

The root crontab can be inspected using:

```bash
sudo crontab -l
```

## Services and Tools

The main services and tools used in this project include:

- OpenSSH
- UFW
- AppArmor
- sudo
- cron
- LVM
- APT

Service status can be inspected with:

```bash
systemctl status <service>
```

## Technology Comparisons

### Debian vs Rocky Linux

**Debian**

Advantages:

- Highly stable
- Lightweight
- Extensive community support
- Beginner-friendly system administration
- Simple package management using APT

Limitations:

- Packages may not always provide the newest versions
- Less focused on enterprise environments than RHEL-based systems

**Rocky Linux**

Advantages:

- Enterprise-oriented Linux distribution
- Compatible with the Red Hat Enterprise Linux ecosystem
- Strong security controls using SELinux

Limitations:

- More complex configuration
- Smaller beginner-oriented community compared with Debian

For this project, I chose **Debian** because it provides a simple and stable environment for learning Linux fundamentals while meeting the Born2beRoot requirements.

### AppArmor vs SELinux

**AppArmor**

- Uses path-based security profiles
- Easier to configure and understand
- Commonly used on Debian and Ubuntu systems

**SELinux**

- Uses label-based mandatory access control
- Provides detailed security policies
- Commonly used in Red Hat-based systems

AppArmor provides a simpler introduction to mandatory access control, while SELinux offers more granular policy management.

### UFW vs firewalld

**UFW**

- Simple firewall management
- Easy command syntax
- Suitable for basic server configurations

**firewalld**

- Supports zones and dynamic firewall configurations
- Commonly used in enterprise Linux environments
- Provides more advanced network rule management

UFW was used in this project because its simple interface is well suited for the required firewall configuration.

### VirtualBox vs UTM

**VirtualBox**

- Widely used virtualization platform
- Common in educational environments
- Easy virtual machine management
- Used on 42 school computers

**UTM**

- Built on QEMU
- Well suited for Apple Silicon systems
- Supports both virtualization and emulation

VirtualBox was used for the project because it is the virtualization platform provided in the 42 environment.

## Useful Verification Commands

Some useful commands for checking the system configuration include:

```bash
# Operating system
uname -a

# Disk and partitions
lsblk

# LVM
sudo lvdisplay

# Users
getent passwd

# Groups
getent group

# Current user groups
groups

# SSH
systemctl status ssh

# Firewall
sudo ufw status

# sudo permissions
sudo -l

# AppArmor
sudo aa-status

# Memory
free -m

# Disk usage
df -h

# Running services
systemctl --type=service

# Root cron jobs
sudo crontab -l
```

## Resources

The following resources were used while completing the project:

- **42 Born2beRoot Subject PDF**
  Used as the primary specification for project requirements, mandatory configurations, and evaluation criteria.

- **Debian Documentation**
  Used to study system installation, package management, networking, SSH, user management, and AppArmor.

- **Rocky Linux Documentation**
  Used primarily for comparison with Debian and for understanding enterprise Linux concepts such as SELinux and firewalld.

- **Linux Manual Pages (`man`)**
  Used to understand Linux commands, system utilities, and configuration tools including `useradd`, `usermod`, `passwd`, `sudo`, `ufw`, `cron`, `ssh`, `lsblk`, `df`, and `free`.

- **Born2beRoot community guides**
  Used as supplementary learning material for understanding the project workflow, configuration process, and common mistakes.

## AI Usage

Artificial Intelligence tools were used strictly as a learning and documentation aid during this project.

AI assistance was used for:

- Clarifying Linux concepts such as virtualization, LVM, SSH, firewall behavior, permissions, and user management
- Explaining Linux commands and configuration files
- Understanding differences between system administration technologies
- Organizing project notes and documentation
- Improving the clarity and structure of this README

Technical information was verified using the project subject, official documentation, and Linux manual pages.