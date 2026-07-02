# 🚀 Day 05 – Linux Service Troubleshooting (Nginx)

## 📌 Objective

To practice Linux service troubleshooting by checking the Nginx process, service status, process IDs, logs, identifying a service startup issue, and verifying that the web server was running successfully.

---

## 🛠️ Service Selected

**Service:** Nginx

**Purpose:** Nginx is a high-performance web server and reverse proxy server used to host web applications and websites.

---

## ✅ Step 1 – Check Running Process

### Command

```bash
ps -ef | grep nginx
```

### Observation

The output showed one **Master Process** and four **Worker Processes**, confirming that the Nginx process was running.

📷 **Screenshot:** `Screenshots/01-process-check.png`

---

## ✅ Step 2 – Check Service Status

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

📷 **Screenshot:** `Screenshots/02-service-status.png`

---

## ✅ Step 3 – Check Process ID (PID)

### Command

```bash
pgrep nginx
```

### Observation

The command returned multiple PIDs.

The first PID belongs to the **Master Process**, while the remaining PIDs belong to the **Worker Processes**.

📷 **Screenshot:** `Screenshots/03-pgrep.png`

---

## ✅ Step 4 – Check Recent Logs

### Command

```bash
journalctl -u nginx -n 10
```

### Observation

The logs contained the previous **bind() failed** error caused by Port 80 already being in use. The latest log entries confirmed that the Nginx service started successfully after the issue was resolved.

📷 **Screenshot:** `Screenshots/04-journalctl-logs.png`

---

## ✅ Step 5 – Verify the Web Page

### Command

```bash
curl http://localhost
```

### Observation

Verified that the web page was being served successfully by the web server.

📷 **Screenshot:** `Screenshots/05-curl-localhost.png`

---

## ✅ Step 6 – Verify HTTP Response Header

### Command

```bash
curl -I http://localhost
```

### Observation

The HTTP response header confirmed that the request was being served by **Nginx**.

📷 **Screenshot:** `Screenshots/06-curl-header.png`

---

## ✅ Step 7 – Rename Default Web Page and Verify

### Commands

```bash
sudo mv /var/www/html/index.html /var/www/html/index.html.bak
ls -l /var/www/html
```

### Observation

The Apache default `index.html` file was renamed. After refreshing the browser, the default **Nginx Welcome Page** was displayed.

📷 **Screenshot:** `Screenshots/07-rename-and-verify.png`

---

## ✅ Step 8 – Verify Nginx Welcome Page

### Observation

Successfully verified that the default Nginx Welcome Page was displayed in the browser.

📷 **Screenshot:** `Screenshots/08-nginx-welcome-page.png`

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

📷 **Note:** Screenshots for these troubleshooting steps were not captured during the practical.

---

## 📚 Commands Practiced

```bash
ps -ef | grep nginx
systemctl status nginx
pgrep nginx
journalctl -u nginx -n 10
journalctl -xeu nginx.service
sudo lsof -i :80
sudo systemctl stop apache2
sudo systemctl start nginx
curl http://localhost
curl -I http://localhost
sudo mv /var/www/html/index.html /var/www/html/index.html.bak
ls -l /var/www/html
```

---

## 🎯 What I Learned

* Difference between a Linux process and a Linux service.
* How to check running processes using `ps` and `pgrep`.
* How to verify service status using `systemctl`.
* How to analyze service logs using `journalctl`.
* How to identify a port conflict using `lsof`.
* How to verify a web server using `curl`.
* How to troubleshoot and restore a failed Linux service by identifying the root cause instead of simply restarting the service.
