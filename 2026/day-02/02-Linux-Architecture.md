# Linux Architecture Notes

## Core Components of Linux

### Hardware

* Physical components such as CPU, RAM, Disk, and Network devices.

### Kernel

* The core of the Linux operating system.
* Manages hardware resources, memory, processes, filesystems, and devices.
* Acts as an interface between hardware and user applications.

### Shell

* A command-line interpreter that accepts user commands and communicates with the kernel.

### User Space

* Where user applications (Bash, Python, Docker, Nginx, etc.) execute.

### System Libraries

* Collections of reusable functions that applications use to communicate with the kernel through system calls.

### System Utilities

* Built-in Linux tools such as `ls`, `cp`, `mv`, `grep`, and `find` used for everyday system administration.

---

# Processes in Linux

A **process** is a running instance of a program.

When a program is executed (for example, `ping google.com`), Linux creates a process and assigns it a unique **Process ID (PID)**.

Useful commands to view processes:

* `ps`
* `ps -ef`
* `top`

---

# Process States

* **Running (R):** Currently executing on the CPU.
* **Sleeping (S):** Waiting for an event or resource.
* **Stopped (T):** Suspended (for example, by pressing **Ctrl + Z**) until resumed.
* **Zombie (Z):** Process has finished execution, but its parent has not yet collected its exit status.

---

# Five Commands Used Daily

| Command      | Purpose                                         |
| ------------ | ----------------------------------------------- |
| `ps`         | Display running processes                       |
| `top`        | Monitor CPU, memory, and processes in real time |
| `systemctl`  | Manage system services                          |
| `journalctl` | View system and service logs                    |
| `chmod`      | Change file and directory permissions           |


## 💡 Key Takeaways

* Linux applications run in **User Space** and communicate with the **Kernel**.
* Every running program is a **process** with a unique **PID**.
* **systemd** is the first userspace process (PID 1) and manages system services.
* Understanding processes and services makes troubleshooting Linux systems much easier.

---

## 🚀 Why This Matters

These concepts are essential for:

* Managing Linux servers
* Troubleshooting services
* Monitoring system resources
* Reading logs
* Building a strong DevOps foundation

---

**#90DaysOfDevOps**
