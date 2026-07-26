# 🚀 Day 18/90 – Shell Scripting: Functions & Intermediate Concepts | #90DaysOfDevOps

Today I focused on writing cleaner, modular, and reusable Bash scripts by learning functions, strict mode, local variables, and organizing scripts using a `main()` function.

## 📚 Topics Covered

- Creating and calling Bash functions
- Passing arguments to functions
- Understanding global vs local variables
- Using `set -euo pipefail` for safer scripts
- Organizing scripts with a `main()` function
- Building reusable and maintainable Bash scripts

## 🛠️ Tasks Completed

### ✅ Task 1 – Basic Functions
- Created reusable functions
- Passed arguments using `$1` and `$2`
- Built `greet()` and `add()` functions

### ✅ Task 2 – Disk & Memory Check
- Created separate functions for:
  - Disk usage (`df -h`)
  - Memory usage (`free -h`)
- Used a `main()` function to execute both

### ✅ Task 3 – Strict Mode
- Learned and implemented:
  - `set -e`
  - `set -u`
  - `set -o pipefail`
- Understood how strict mode helps write reliable Bash scripts

### ✅ Task 4 – Local Variables
- Compared global and local variables
- Learned how the `local` keyword limits variable scope
- Understood why local variables prevent unintended side effects

### ✅ Task 5 – System Information Reporter
Built a modular system reporting script using functions to display:
- Hostname & OS information
- System uptime
- Disk usage
- Memory usage
- Top CPU-consuming processes

## 💡 Key Learnings

- Functions improve code reusability and readability.
- `local` variables keep functions independent and reduce bugs.
- `set -euo pipefail` makes Bash scripts safer and more reliable.
- Using a `main()` function creates a clean execution flow.
- Breaking large scripts into smaller functions makes maintenance easier.

## 📂 Files Created

- `functions.sh`
- `disk_check.sh`
- `strict_demo.sh`
- `local_demo.sh`
- `system_info.sh`
- `day-18-scripting.md`

---

### 📌 Progress
✅ Day 18/90 Completed

On to **Day 19** 🚀

#90DaysOfDevOps #DevOps #Linux #ShellScripting #Bash #Automation #TrainWithShubham #GitHub
