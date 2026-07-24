# 🚀 Day 17 – Shell Scripting: Loops, Arguments & Error Handling

## 📌 Overview

Day 17 focused on writing more practical and structured shell scripts by combining loops, command-line arguments, package automation, and basic error handling. The goal was to understand how Bash scripts can automate repetitive tasks and safely handle common system operations.

---

## 📚 Topics Covered

* **For Loop**

  * Iterating through lists
  * Printing multiple values
  * Number generation using brace expansion

* **While Loop**

  * User input with `read`
  * Countdown using conditional loops
  * Loop control until a condition becomes false

* **Command-Line Arguments**

  * Using `$0`, `$1`, `$#`, and `$@`
  * Accepting user input through script arguments
  * Displaying usage instructions when arguments are missing

* **Package Installation Automation**

  * Creating arrays of packages
  * Iterating through packages with `for` loops
  * Checking installed packages using `dpkg -s`
  * Installing missing packages automatically
  * Root user validation using `$EUID`

* **Error Handling**

  * Using `set -e` to stop execution on unexpected failures
  * Using the `||` operator to handle command failures gracefully
  * Creating directories and files with basic error handling

---

## ✅ Tasks Completed

### Task 1 – For Loop

* Created `for_loop.sh`
* Printed a list of five fruits
* Created `count.sh`
* Printed numbers from **1 to 10** using a `for` loop

### Task 2 – While Loop

* Created `countdown.sh`
* Accepted user input
* Counted down to **0**
* Displayed **"Done!"** after completion

### Task 3 – Command-Line Arguments

* Created `greet.sh`

* Accepted a username using `$1`

* Displayed a usage message when no argument was provided

* Created `args_demo.sh`

* Displayed:

  * Script name (`$0`)
  * Number of arguments (`$#`)
  * All arguments (`$@`)

### Task 4 – Install Packages Script

Created `install_packages.sh` that:

* Stores package names in an array
* Loops through each package
* Checks installation status using `dpkg -s`
* Installs missing packages automatically
* Skips already installed packages
* Validates root privileges using `$EUID`

### Task 5 – Error Handling

Created `safe_script.sh` that:

* Uses `set -e`
* Creates `/tmp/devops-test`
* Navigates into the directory
* Creates a file inside it
* Uses the `||` operator for graceful error handling

---

## 🧠 Key Learnings

* Understood the difference between **`for`** and **`while`** loops and when to use each.
* Learned how **command-line arguments** make Bash scripts more flexible and reusable.
* Gained hands-on experience with **basic automation**, **package management**, and **error handling** using `set -e`, `||`, and root privilege checks.

---

## 📂 Files Included

* `for_loop.sh`
* `count.sh`
* `countdown.sh`
* `greet.sh`
* `args_demo.sh`
* `install_packages.sh`
* `safe_script.sh`
* `day-17-scripting.md`

---

## 🎯 Outcome

Day 17 strengthened my understanding of Bash scripting by combining multiple concepts into practical automation tasks. Writing scripts that accept arguments, perform conditional operations, automate package installation, and handle errors has improved my confidence in building reliable shell scripts for DevOps workflows.

---

**#90DaysOfDevOps #DevOpsKaJosh #TrainWithShubham**
