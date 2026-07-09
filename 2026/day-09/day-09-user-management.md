# Day 09 – Linux User & Group Management Challenge

## 📌 Objective

The goal of today's challenge was to understand how Linux manages users, groups, permissions, and shared workspaces. This hands-on lab focused on creating users and groups, assigning permissions, and configuring shared directories for team collaboration.

## 🛠️ Tasks Completed

### ✅ Task 1 – Create Users

* Created users:

  * `tokyo`
  * `berlin`
  * `professor`
* Created home directories for each user.
* Set passwords.
* Verified user creation using `/etc/passwd` and `/home`.

### ✅ Task 2 – Create Groups

* Created groups:

  * `developers`
  * `admins`
* Verified group creation using `/etc/group`.

### ✅ Task 3 – Assign Users to Groups

* Added `tokyo` to the `developers` group.
* Added `berlin` to both `developers` and `admins`.
* Added `professor` to the `admins` group.
* Verified group membership using the `groups` command.

### ✅ Task 4 – Shared Directory

* Created `/opt/dev-project`.
* Changed the group owner to `developers`.
* Set directory permissions to `775`.
* Tested file creation as different users.
* Verified directory permissions and ownership.

### ✅ Task 5 – Team Workspace

* Created user `nairobi`.
* Created group `project-team`.
* Added `nairobi` and `tokyo` to `project-team`.
* Created `/opt/team-workspace`.
* Changed the group owner to `project-team`.
* Applied `775` permissions.
* Verified access by creating files as `nairobi`.

## 📚 Commands Practiced

* `useradd`
* `passwd`
* `groupadd`
* `usermod`
* `groups`
* `mkdir`
* `chgrp`
* `chmod`
* `touch`
* `ls -l`
* `ls -ld`
* `sudo -u`

## 🎯 Key Learnings

* Understood the difference between Linux users and groups.
* Learned the purpose of primary and secondary groups.
* Practiced assigning users to multiple groups.
* Configured shared directories for team collaboration.
* Learned how group ownership and `775` permissions work together.
* Verified permissions and group membership using Linux commands.
* Understood how Linux uses users, groups, and permissions to provide secure access to shared resources.

## 🚀 Outcome

Successfully completed the Day 09 Linux User & Group Management Challenge with hands-on practice in user administration, group management, shared directory configuration, permission management, and access verification.
