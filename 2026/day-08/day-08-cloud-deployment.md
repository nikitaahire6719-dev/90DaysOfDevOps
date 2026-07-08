# Day 08 – Cloud Server Setup: Docker, Nginx & Web Deployment

## 🚀 Objective

Today's goal was to deploy a real web server on the cloud and understand how remote server management works in a real DevOps environment.

Instead of working on a local machine, I deployed and managed an Ubuntu server on AWS EC2, connected to it using SSH, installed Docker and Nginx, configured the Security Group for web access, and verified that the web server was accessible from the internet.

---

## 🛠️ Technologies Used

* AWS EC2
* Ubuntu Linux
* SSH
* Docker
* Nginx
* AWS Security Groups

---

## 📋 Commands Used

### Connect to EC2 Instance

```bash
ssh -i devops-key-pair.pem ubuntu@<public-ip>
```

### Update the System

```bash
sudo apt update
sudo apt upgrade -y
```

### Install Docker

```bash
sudo apt install docker.io -y
docker --version
sudo systemctl start docker
sudo systemctl enable docker
sudo systemctl status docker
```

### Install Nginx

```bash
sudo apt install nginx -y
nginx -v
sudo systemctl start nginx
sudo systemctl enable nginx
sudo systemctl status nginx
```

### View Nginx Logs

```bash
cat /var/log/nginx/access.log
```

### Save Logs

```bash
cat /var/log/nginx/access.log > ~/nginx-logs.txt
```

### Copy Logs to Local Machine

```bash
scp -i devops-key-pair.pem ubuntu@<public-ip>:~/nginx-logs.txt .
```

---

## 📚 Challenges Faced

* Received **"Permissions 0644 are too open"** while connecting via SSH. Fixed it by changing the key permissions using `chmod 400`.
* Lost the SSH connection because of a temporary power outage and internet interruption. Reconnected successfully without affecting the EC2 instance.
* Docker and Nginx were not installed initially, so I verified their availability first and then installed them.
* The Nginx webpage was not opening at first because HTTP (Port 80) was not allowed in the Security Group. After adding the inbound rule, the webpage became accessible.

---

## ✅ What I Learned

* How to launch and manage an AWS EC2 instance.
* How to securely connect to a remote Linux server using SSH.
* How to install, start, enable, and verify Docker and Nginx services.
* How AWS Security Groups control inbound traffic.
* How to access and save Nginx access logs for troubleshooting.
* The importance of troubleshooting and verifying each step instead of assuming everything is configured correctly.

---

## 💡 Why This Matters for DevOps

This practical introduced the complete workflow of deploying and managing a cloud server.

It covered key DevOps concepts such as:

* Cloud infrastructure provisioning
* Remote Linux server administration
* Secure SSH connectivity
* Service installation and management
* Web server deployment
* Firewall and Security Group configuration
* Log monitoring and troubleshooting

These are fundamental skills used by DevOps engineers in real production environments.

---

## 📸 Screenshots

* ✅ SSH Connection
* ✅ Nginx Welcome Page
* ✅ Docker & Nginx Installation
* ✅ Nginx Log File

---

## 🎯 Outcome

Successfully launched an AWS EC2 instance, connected via SSH, installed Docker and Nginx, configured HTTP access through the Security Group, deployed a live web server, and verified it through a browser. Finally, extracted and saved the Nginx access logs as part of the deployment process.
