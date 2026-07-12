# Day 12 – Breather & Revision (Days 01–11)

## Objective

Today's goal was to revise and reinforce everything I learned during the first 11 days instead of learning something new.

---

## Revision Summary

### ✅ Mindset Review

* My goal remains the same: Become a DevOps Engineer.
* I will continue following the 90 Days of DevOps roadmap consistently.
* I want to strengthen my Linux fundamentals before moving deeper into DevOps tools.

### ✅ Process & Service Management

Commands revised:

* `ps`
* `ps -ef`
* `systemctl status ssh`
* `journalctl -u ssh`

**Observations**

* `ps` displays the processes running in the current terminal.
* `ps -ef` shows all running processes with detailed information.
* `systemctl status` helps check whether a service is active, inactive, or failed.
* `journalctl` is useful for identifying the root cause of service failures.

---

### ✅ File Operations Practice

Practiced:

* mkdir
* cp
* echo >>
* cat
* ls -l
* chmod

I also corrected mistakes related to file paths and permissions while practicing.

---

### ✅ User & Ownership Practice

Practiced:

* useradd
* userdel
* chown
* chmod
* ls -l

Verified ownership and permissions after making changes.

---

## Top 5 Commands for Troubleshooting

* `ls -l`
* `pwd`
* `systemctl status`
* `journalctl -u`
* `ps -ef`

---

## Self Check

### 1. Which three commands save you the most time?

* `ls -l` – Helps me verify permissions, ownership, and file details.
* `pwd` – Confirms my current working directory.
* `systemctl status` – Quickly checks whether a service is healthy or not.

### 2. How do I check if a service is healthy?

1. `systemctl status <service>`
2. `journalctl -u <service>`
3. `ps -ef` or `pgrep` to verify the process if required.

### 3. How do I safely change ownership and permissions?

* Use `chown` to change ownership.
* Use `chmod` to change permissions.
* Verify current ownership and permissions using `ls -l` before making changes.
* Avoid giving unnecessary permissions like `777`.
* Verify changes again after applying them.

Example:

```bash
sudo chown -R username:groupname project-folder
chmod 644 filename
```

### 4. Focus for the Next 3 Days

* Improve Linux command confidence.
* Practice commands daily without looking at notes.
* Learn Shell Scripting with a strong understanding of when and why commands are used.
* Continue improving troubleshooting skills through hands-on practice.

---

## Key Learning

Today I experienced a real SSH service issue. Instead of guessing the solution, I learned how to troubleshoot it by checking the service status, reading logs, identifying the root cause, and verifying the fix. This helped me understand that troubleshooting is more important than memorizing commands.

---

## Day 12 Takeaway

Linux is the main gate to the DevOps journey. The more comfortable I become with Linux, the easier it will be to learn Shell Scripting, Git, Docker, Kubernetes, Jenkins, Terraform, Ansible, and AWS.
