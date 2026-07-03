# Day 6 – Linux File Input/Output Practice

## Objective

The objective of this practice was to understand basic Linux file input/output operations. I learned how to create files, write data, append data, display file contents, and use different commands to read specific parts of a file.

---

## Commands Practiced

### 1. Create a File

```bash
touch notes.txt
```

Creates an empty file named `notes.txt` if it does not already exist.

---

### 2. Write Data to a File (Overwrite)

```bash
echo "I am Nikita Ahire" > notes.txt
```

The `>` operator writes data to a file. If the file already contains data, it is overwritten.

---

### 3. Append Data to a File

```bash
echo "I will become a successful DevOps Engineer by the end of 2026." >> notes.txt
```

The `>>` operator appends new data to the end of the file without removing the existing content.

---

### 4. Display File Contents

```bash
cat notes.txt
```

Displays the complete contents of the file.

---

### 5. Display the First Lines of a File

```bash
head notes.txt
head -5 notes.txt
```

* `head` displays the first 10 lines by default.
* `head -5` displays only the first 5 lines.

---

### 6. Display the Last Lines of a File

```bash
tail notes.txt
tail -5 notes.txt
```

* `tail` displays the last 10 lines by default.
* `tail -5` displays only the last 5 lines.

---

### 7. Use the `tee` Command

```bash
echo "I used tee command" | tee notes.txt
```

The `tee` command displays the output on the terminal and writes it to a file. Without the `-a` option, it overwrites the file.

---

### 8. Append Using `tee -a`

```bash
echo "This line was added using tee -a" | tee -a notes.txt
```

The `-a` option appends the output to the existing file instead of overwriting it.

---

## Key Learnings

* `touch` creates an empty file.
* `>` overwrites the existing contents of a file.
* `>>` appends data to the end of a file.
* `cat` displays the complete file.
* `head` shows the first lines of a file.
* `tail` shows the last lines of a file.
* `tee` writes output to a file and displays it on the terminal.
* `tee -a` appends output to a file while also displaying it on the terminal.

---

## Conclusion

This practice helped me understand the basics of Linux file input/output operations. These commands are essential for working with configuration files, log files, automation scripts, and daily system administration tasks in DevOps.
