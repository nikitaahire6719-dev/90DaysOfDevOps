# Day 04 – Linux Process, Services & Log Management

## 📌 Objective

Today's goal was to understand how Linux administrators and DevOps engineers troubleshoot systems by inspecting **processes**, **services**, and **logs** instead of simply memorizing commands.

---

## 📚 Topics Covered

### 🔹 Processes

* What is a Process?
* Program vs Process
* Process ID (PID)
* Why Linux creates processes
* Real-world process monitoring

### 🔹 Commands Practiced

```bash
ps
ps -ef
ps aux
pgrep cron
pgrep ssh
```

**Key Learning**

* `ps` displays running processes.
* `ps -ef` shows all running processes with detailed information.
* `pgrep` searches for a process by name and returns its PID.

---

### 🔹 Services

Commands Practiced

```bash
systemctl status ssh
systemctl status cron
systemctl start ssh
systemctl stop ssh
systemctl restart ssh
systemctl enable ssh
systemctl disable ssh
```

**Key Learning**

* Checked service status.
* Understood the difference between:

  * `active (running)`
  * `inactive (dead)`
  * `failed`

---

### 🔹 Logs

Commands Practiced

```bash
journalctl -u ssh
journalctl -u cron
tail -n 20 /var/log/syslog
```

**Key Learning**

* Logs record system and application events.
* Logs help identify the root cause of issues.
* They provide evidence of service starts, stops, and errors.

---

## 🖥️ Practical Work

* Inspected running processes using `ps` and `pgrep`.
* Checked SSH and Cron service status.
* Practiced starting, stopping, restarting, enabling, and disabling services.
* Viewed service logs using `journalctl`.
* Explored system logs using `tail`.

---

## 🏢 Real-World Troubleshooting Workflow

```
Application/Website Issue
        ↓
Check Running Process
        ↓
Check Service Status
        ↓
Inspect Logs
        ↓
Identify Root Cause
        ↓
Fix the Issue
        ↓
Verify the Service
```

---

## 💡 Key Takeaway

Today I understood that troubleshooting is not about guessing.

* **Processes** tell us what is currently running.
* **Services** tell us whether an application is active, inactive, or failed.
* **Logs** provide the evidence needed to understand why an issue occurred.

This session helped me understand how Linux administrators and DevOps engineers investigate and resolve real-world server issues.

---

**Day 04 Status:** ✅ Completed
