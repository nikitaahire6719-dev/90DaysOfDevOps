# Day 11 – File Ownership Challenge (chown & chgrp)

## 📖 Overview

On Day 11 of my **#90DaysOfDevOps** journey, I explored Linux file ownership and learned how to manage file and directory ownership using `chown` and `chgrp`. This challenge focused on understanding the relationship between users, groups, and file ownership, along with applying ownership changes recursively.

---

## 🎯 Objectives

* Understand Linux file ownership (Owner & Group)
* Change file owner using `chown`
* Change file group using `chgrp`
* Change both owner and group using a single `chown` command
* Apply recursive ownership changes with `chown -R`
* Practice ownership management through a real-world challenge

---

## ✅ Tasks Completed

### Task 1 – Understanding File Ownership

* Identified file owner and group using `ls -l`
* Understood the difference between file owner and group ownership

### Task 2 – Changing File Owner

* Created `devops-file.txt`
* Changed ownership from the default user to **tokyo**
* Changed ownership from **tokyo** to **berlin**
* Verified each ownership change

### Task 3 – Changing File Group

* Created `team-notes.txt`
* Created the **heist-team** group
* Changed the file group using `chgrp`
* Verified the changes

### Task 4 – Changing Owner and Group Together

* Created `project-config.yaml`
* Changed both owner (**professor**) and group (**heist-team**) using a single `chown` command
* Changed ownership of the `app-logs` directory
* Verified the results

### Task 5 – Recursive Ownership

* Created a nested project directory structure
* Created the **planners** group
* Applied recursive ownership changes using `chown -R`
* Verified ownership of all files and subdirectories using `ls -lR`

### Task 6 – Practice Challenge

* Created multiple users and groups
* Assigned different owners and groups to project files
* Verified all ownership assignments successfully

---

## 🛠️ Commands Practiced

```bash
ls -l
ls -ld
ls -lR
chown
chgrp
chown owner:group
chown -R
useradd
groupadd
userdel
groupdel
```

---

## 📸 Screenshots Included

* Task 1 – File Ownership
* Task 2 – Owner Change (Tokyo)
* Task 2 – Owner Change (Berlin)
* Task 3 – Group Change
* Task 4 – Owner & Group Change
* Task 4 – Directory Ownership
* Task 5 – Recursive Ownership
* Task 6 – Bank Heist Challenge

---

## 📚 Key Learnings

* Every Linux file has an owner and an associated group.
* `chown` changes the owner and can also change the group.
* `chgrp` changes only the group ownership.
* Recursive ownership (`chown -R`) updates all files and subdirectories within a directory.
* Verifying changes using `ls -l`, `ls -ld`, and `ls -lR` is an important practice after making ownership changes.

---

### 🚀 Day 11 Successfully Completed

Hands-on practice with Linux file ownership improved my understanding of user and group management, which is an essential skill for Linux administration and DevOps.
