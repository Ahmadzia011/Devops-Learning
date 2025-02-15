
# 🐧 Linux Commands Practice Guide  

## 🔹 Introduction to Linux  

Linux is an open-source, Unix-like operating system that provides a powerful command-line interface (CLI) for managing files, processes, users, and system configurations.  

## 🔹 Linux Directory Structure  

In Linux, the **filesystem hierarchy** follows a structured format. Here are some key directories:  

| Directory | Description |
|-----------|------------|
| **/**  | Root directory (everything starts from here) |
| **/bin/** | Essential user binaries (e.g., `ls`, `cp`, `mv`) |
| **/sbin/** | System administration binaries (e.g., `shutdown`, `fdisk`) |
| **/usr/** | User programs and applications (`/usr/bin`, `/usr/sbin`) |
| **/home/** | User directories (`/home/user`) |
| **/etc/** | System configuration files |
| **/var/** | Variable files like logs (`/var/log`) |
| **/tmp/** | Temporary files (cleared on reboot) |
| **/mnt/** | Mounted filesystem (USB, network drives) |
| **/dev/** | Device files (e.g., `/dev/sda` for hard drives) |
| **/proc/** | Virtual filesystem for system information |

---

## 🔹 Basic Linux Commands  

### 📂 **File and Directory Management**  

| Command | Description |
|---------|------------|
| `ls` | List files and directories |
| `ls -l` | Detailed list view (permissions, size, owner) |
| `ls -a` | Show hidden files |
| `mkdir <dir>` | Create a new directory |
| `rmdir <dir>` | Remove an empty directory |
| `rm <file>` | Delete a file |
| `rm -r <dir>` | Delete a directory and its contents |
| `mv <source> <destination>` | Move/rename files or directories |
| `cp <source> <destination>` | Copy files |
| `touch <file>` | Create an empty file |

---
