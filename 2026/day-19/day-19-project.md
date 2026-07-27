# 🚀 Day 19/90 – Shell Scripting Project: Log Rotation, Backup & Crontab

## 📌 Overview

Today I worked on real-world shell scripting automation by building practical maintenance scripts. The focus was on log management, automated backups, cron scheduling, and combining multiple scripts into a single maintenance workflow.

---

## ✅ Tasks Completed

### **Task 1: Log Rotation Script (`log_rotate.sh`)**

* Accepted a log directory as a command-line argument.
* Validated user input and checked whether the directory exists.
* Compressed `.log` files older than **7 days** using `gzip`.
* Deleted compressed `.gz` files older than **30 days**.
* Counted and displayed the number of files compressed and deleted.

### **Task 2: Server Backup Script (`backup.sh`)**

* Accepted source and destination directories as arguments.
* Created a timestamped backup archive using `tar`.
* Generated backups in the format:

  ```
  backup-YYYY-MM-DD.tar.gz
  ```
* Verified successful archive creation.
* Displayed archive name and size.
* Removed backup archives older than **14 days**.

### **Task 3: Cron Scheduling**

Learned cron syntax and prepared scheduling entries for:

* Daily log rotation at **2:00 AM**
* Weekly backup every **Sunday at 3:00 AM**
* Health check script every **5 minutes**

### **Task 4: Scheduled Maintenance Script (`maintenance.sh`)**

* Created a master maintenance script.
* Executed both `log_rotate.sh` and `backup.sh`.
* Logged execution details with timestamps.
* Stored maintenance logs in `maintenance.log`.
* Prepared cron scheduling for automated daily execution.

---

## 🛠 Commands & Concepts Practiced

* Bash Variables
* Command-Line Arguments (`$1`, `$2`)
* Conditional Statements (`if`, `else`)
* File & Directory Validation (`-d`, `-f`)
* `find`
* `gzip`
* `tar`
* `date`
* `du`
* `cut`
* `wc`
* `cron` / `crontab`
* Output Redirection (`>>`)
* Shell Script Automation

---

## 📚 Key Learnings

* Automated log rotation and cleanup using `find` and `gzip`.
* Built timestamped backup archives with verification and retention policies.
* Learned how to schedule automation using **Cron Jobs**.
* Combined multiple scripts into a centralized maintenance workflow.
* Improved understanding of Linux automation and Bash scripting best practices.

---

✅ **Day 19 Complete**
