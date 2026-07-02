# 🚀 Day 05 – Linux Service Troubleshooting (Nginx)

## 📌 Objective

To troubleshoot the Nginx service by checking its process, service status, logs, identifying the root cause of failure, and restoring the service successfully.

---

# 🛠️ Service Selected

**Service:** Nginx

**Purpose:**
Nginx is a high-performance web server and reverse proxy server used to host web applications and websites.

---

# ✅ Step 1 – Check Running Process

### Command

```bash
ps -ef | grep nginx
```

### Observation

The output showed one **Master Process** and four **Worker Processes**, confirming that the Nginx process was running.

📷 **Screenshot:** `01-process-check.png`

---

# ✅ Step 2 – Check Service Status

### Command

```bash
systemctl status nginx
```

### Observation

The service status displayed:

```
Active: active (running)
```

This confirmed that the Nginx service was running successfully.

📷 **Screenshot:** `02-service-status.png`

---

# ✅ Step 3 – Check Process ID (PID)

### Command

```bash
pgrep nginx
```

### Observation

The command returned five PIDs.

The first PID belongs to the **Master Process**, while the remaining PIDs belong to the **Worker Processes**.

📷 **Screenshot:** `03-pgrep.png`

---

# ✅ Step 4 – Check Recent Logs

### Command

```bash
journalctl -u nginx -n 10
```

### Observation

The logs showed the previous **bind() failed** error because Apache was already using Port 80.

The latest log entries confirmed that Nginx started successfully after resolving the issue.

📷 **Screenshot:** `04-nginx-logs.png`

---

# 🛠️ Troubleshooting Performed

During the practical, Nginx initially failed to start.

The following troubleshooting steps were performed:

* Checked the service status.
* Reviewed the Nginx logs.
* Identified the error:

  ```
  bind() to 0.0.0.0:80 failed (98: Address already in use)
  ```
* Checked which process was using Port 80.
* Found that **Apache2** was already using Port 80.
* Stopped the Apache service.
* Started the Nginx service again.
* Verified that the service, processes, and PIDs were running correctly.

📷 **Screenshots:**

* `05-nginx-error.png`
* `06-port80-check.png`
* `07-stop-apache.png`
* `08-start-nginx.png`

---

# 📚 Commands Practiced

```bash
ps -ef | grep nginx
systemctl status nginx
pgrep nginx
journalctl -u nginx -n 10
journalctl -xeu nginx.service
sudo lsof -i :80
sudo systemctl stop apache2
sudo systemctl start nginx
```

---

# 🎯 What I Learned

* Difference between a Linux **process** and a **service**.
* How to check running processes using `ps` and `pgrep`.
* How to verify service status using `systemctl`.
* How to analyze service logs using `journalctl`.
* How to identify a port conflict using `lsof`.
* How to troubleshoot and restore a failed service by finding the root cause instead of simply restarting it.
