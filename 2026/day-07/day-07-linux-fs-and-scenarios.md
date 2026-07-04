# 🚀 Day 07 – Linux File System Hierarchy & Scenario-Based Practice

## 📖 Overview

Today I learned about the Linux File System Hierarchy and practiced solving real-world troubleshooting scenarios commonly faced by DevOps Engineers. I explored important system directories, understood their purpose, and completed hands-on scenario-based exercises to strengthen my Linux fundamentals.

---

# 📂 Linux File System Hierarchy

## Core Directories (Must Know)

### 📁 / (Root)
- The starting point of the Linux file system.
- Every file and directory branches from here.

**I would use this** to navigate to the root of the Linux file system.

---

### 🏠 /home
- Contains home directories of normal users.
- Each user stores personal files in their own directory.

**I would use this** to access user files and home directories.

---

### 👑 /root
- Home directory of the root (superuser).
- Separate from normal user directories.

**I would use this** to store files that should only be accessed by the root user.

---

### ⚙️ /etc
- Stores system, application, and service configuration files.

Examples:
- `/etc/environment` → Global environment variables.
- `/etc/adduser.conf` → Default settings for new users.

**I would use this** whenever I need to configure the Linux system or services.

---

### 📋 /var/log
- Stores system, application, and service log files.
- Essential for monitoring and troubleshooting.

Important logs:
- `auth.log` → Authentication-related logs.
- `syslog` → General system and service logs.

**I would use this** to investigate system or application issues.

---

### 🗂️ /tmp
- Stores temporary files created by users and applications.
- Files are usually removed after reboot.

**I would use this** for temporary files that are not required permanently.

---

## Additional Directories (Good to Know)

### 📦 /bin
- Contains essential command binaries.
- On modern Linux systems, it is a symbolic link to `/usr/bin`.

**I would use this** to access essential Linux commands.

---

### 💻 /usr/bin
- Stores most user command binaries.

Examples:
- `ls`
- `mkdir`
- `mv`
- `cp`
- `cat`

**I would use this** to locate Linux commands and utilities.

---

### 📥 /opt
- Used for optional and third-party software installations.

Examples:
- Google Chrome
- Visual Studio Code

**I would use this** to check externally installed applications.

---

# 🛠️ Scenario-Based Practice

## ✅ Scenario 1 – Service Not Starting

**Problem:** A service called **myapp** failed to start after a server reboot.

### Step 1
```bash
systemctl status myapp
```

**Why:** Check whether the service is active, failed, or stopped.

### Step 2
```bash
journalctl -u myapp -n 50
```

**Why:** Review the last 50 log entries to identify the cause.

### Step 3
```bash
systemctl is-enabled myapp
```

**Why:** Verify whether the service starts automatically after boot.

### Step 4
```bash
systemctl restart myapp
```

**Why:** Restart the service after resolving the issue.

---

## ✅ Scenario 2 – High CPU Usage

### Step 1
```bash
top
```
or
```bash
htop
```

**Why:** Monitor running processes and CPU usage in real time.

### Step 2
```bash
ps aux --sort=-%cpu | head -10
```

**Why:** Find the processes consuming the highest CPU.

### Step 3
```bash
sudo renice +10 -p PID
```

**Why:** Reduce the CPU priority of the process.

### Step 4
```bash
kill PID
```

**Why:** Stop the process if it continues consuming excessive CPU.

---

## ✅ Scenario 3 – Finding Service Logs

**Problem:** Find logs for the **docker** service.

### Step 1
```bash
systemctl status docker
```

**Why:** Check the current service status.

### Step 2
```bash
journalctl -u docker -n 50
```

**Why:** View the latest 50 log entries.

### Step 3
```bash
journalctl -u docker -f
```

**Why:** Monitor logs in real time.

---

## ✅ Scenario 4 – File Permission Issue

**Problem:** `backup.sh` shows **Permission denied**.

### Step 1
```bash
ls -l /home/user/backup.sh
```

**Why:** Check the current file permissions.

### Step 2
```bash
chmod +x /home/user/backup.sh
```

**Why:** Add execute permission to the script.

### Step 3
```bash
ls -l /home/user/backup.sh
```

**Why:** Verify that execute permission has been added.

### Step 4
```bash
./backup.sh
```

**Why:** Execute the script to confirm the issue is resolved.

---

# 🎯 Key Takeaways

- Learned the Linux File System Hierarchy.
- Understood where Linux stores configuration files, logs, binaries, and user data.
- Practiced real-world troubleshooting scenarios.
- Improved Linux troubleshooting skills using `systemctl`, `journalctl`, `top`, `ps`, `chmod`, and `kill`.
- Built a stronger foundation for DevOps and production support.

---

## 🚀 Day 07 Status

- ✅ Linux File System Hierarchy Completed
- ✅ Hands-on Linux Practice Completed
- ✅ All Scenario-Based Questions Completed
- ✅ Notes Prepared
- ✅ Ready for Day 08

---

**#90DaysOfDevOps** | **#DevOpsKaJosh** | **#TrainWithShubham**
