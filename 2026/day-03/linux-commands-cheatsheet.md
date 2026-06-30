# Linux Commands Cheat Sheet

## Process Management

* **&** – Add this character at the end of a command to run it in the background.
* **ps aux** – Display a full snapshot of all running processes.
* **pgrep <process_name>** – Find a process by its name.
* **kill <PID>** – Terminate a process using its Process ID.
* **top** – Display and monitor running processes in real time.

---

## File System

* **pwd** – Display the current working directory.
* **wc <file>** – Count the number of lines, words, and characters in a file.
* **head <file>** – Display the first 10 lines of a file.
* **tail <file>** – Display the last 10 lines of a file.
* **grep "pattern" <file>** – Search for a specific text pattern in a file.
* **find** – Search for files and directories.
* **chmod 777 <file>** – Change file permissions.
* **chown user:group <file>** – Change the ownership of a file.
* **du -h** – Show the disk usage of files and directories.
* **df -h** – Display available and used disk space.

---

## Networking Troubleshooting

* **ip addr** – Display all network interfaces and their IP addresses.
* **ping <host>** – Check network connectivity with another host.
* **traceroute <host>** – Trace the path packets take to reach a destination.
* **wget <URL>** – Download files from the internet.
* **host <domain>** – Display the IP address associated with a domain.
* **nslookup <domain>** – Retrieve DNS information for a domain.
* **curl <URL>** – Send an HTTP request and view the server response.
