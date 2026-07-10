# Day 10 – File Permissions & File Operations Challenge

## Objective

Learned how to create, read, and manage files in Linux while understanding and modifying file permissions using the `chmod` command.

---

## Files Created

* `devops.txt`
* `notes.txt`
* `script.sh`
* `project/` (Directory)

---

## Permission Changes

| File/Directory | Before       | After              | Description                                                                                        |
| -------------- | ------------ | ------------------ | -------------------------------------------------------------------------------------------------- |
| `script.sh`    | `-rw-r--r--` | `-rwxr-xr-x` (755) | Added execute permission and successfully executed the script.                                     |
| `devops.txt`   | `-rw-r--r--` | `-r--r--r--` (444) | Removed write permission to make the file read-only.                                               |
| `notes.txt`    | `-rw-r--r--` | `-rw-r-----` (640) | Restricted access so only the owner can write, the group can read, and others have no permissions. |
| `project/`     | Default      | `drwxr-xr-x` (755) | Created a directory with standard permissions.                                                     |

---

## Commands Used

```bash
pwd
ls -l
touch devops.txt
echo "This is my Day 10 Linux practice." > notes.txt
vim script.sh
cat notes.txt
vim -R script.sh
head -n 5 /etc/passwd
tail -n 5 /etc/passwd
chmod +x script.sh
./script.sh
chmod -w devops.txt
chmod 640 notes.txt
mkdir project
chmod 755 project
ls -ld project
```

---

## Screenshots Included

* File creation
* Reading file contents
* Initial file permissions
* Permission changes using `chmod`
* Executing `script.sh`
* Directory permissions
* Final `ls -l` output

---

## What I Learned

* Understood Linux file permissions (`r`, `w`, `x`) and the roles of Owner, Group, and Others.
* Learned both symbolic (`+x`, `-w`) and numeric (`755`, `640`, `444`) permission methods using `chmod`.
* Practiced creating files, reading file contents, executing shell scripts, and managing secure file access in Linux.

---

## Conclusion

Day 10 strengthened my understanding of Linux file operations and permission management. I learned how Linux controls access to files and directories, how to modify permissions using `chmod`, and why proper file permissions are essential for system security and DevOps administration.
