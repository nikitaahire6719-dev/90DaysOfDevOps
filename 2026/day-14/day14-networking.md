# Day 14 – Networking Fundamentals & Hands-on Checks

## Objective

Learn the fundamentals of computer networking and practice essential networking commands used in real-world Linux and DevOps troubleshooting.

---

## Quick Concepts

### OSI Model vs TCP/IP Model

| OSI Model              | TCP/IP Model |
| ---------------------- | ------------ |
| Layer 7 – Application  | Application  |
| Layer 6 – Presentation | Application  |
| Layer 5 – Session      | Application  |
| Layer 4 – Transport    | Transport    |
| Layer 3 – Network      | Internet     |
| Layer 2 – Data Link    | Link         |
| Layer 1 – Physical     | Link         |

### Where Common Protocols Fit

* **IP** → Internet (Network) Layer
* **TCP / UDP** → Transport Layer
* **HTTP / HTTPS** → Application Layer
* **DNS** → Application Layer

### Real Example

```text
curl https://google.com

Application Layer (HTTP/HTTPS)
        ↓
Transport Layer (TCP)
        ↓
Internet Layer (IP)
        ↓
Link Layer (Ethernet/Wi-Fi)
```

---

# Hands-on Practice

## 1. Identity Check

### Command

```bash
hostname -I
```

### Observation

* Displays the IP address assigned to the machine.
* Useful for quickly identifying the system's network address.

---

## 2. Reachability Test

### Command

```bash
ping google.com
```

### Observation

* Verified that the destination was reachable.
* Checked latency and confirmed there was no packet loss.

---

## 3. Path Discovery

### Command

```bash
tracepath google.com
```

### Observation

* Observed multiple network hops between my machine and Google.
* Learned that some routers may show **no reply**, which does not always indicate a network failure.

---

## 4. Listening Ports

### Command

```bash
ss -tulpn
```

### Observation

* Found SSH listening on **port 22**.
* Found Nginx listening on **port 80**.
* Understood that `0.0.0.0` means the service accepts connections from all network interfaces.

---

## 5. DNS Resolution

### Command

```bash
dig google.com
```

### Observation

* Successfully resolved the domain to an IPv4 address.
* Learned that `NOERROR` only means the DNS query succeeded—it does **not** always mean an IP address will be returned.

---

## 6. HTTP Header Check

### Command

```bash
curl -I google.com
```

### Observation

* Received **HTTP 301 Moved Permanently**.
* Learned that the web server was reachable and instructed the client to use another URL.

---

## 7. Connection Snapshot

### Command

```bash
netstat -an | head
```

### Observation

* Viewed active network connections.
* Identified listening services and existing TCP connections.

---

# Mini Task – Port Probe

### Identify Listening Port

SSH was listening on **port 22**.

### Test

```bash
nc -zv localhost 22
```

### Observation

* Successfully connected to the SSH service.
* Confirmed that port 22 was reachable.

### If the check failed...

Next steps would be:

* Verify the SSH service is running.
* Check firewall rules.
* Confirm the service is listening using:

```bash
ss -tulpn
```

---

# Reflection

### Which command gives the fastest signal when something is broken?

`ping` is usually the quickest way to verify whether the target machine is reachable.

---

### Which layer would I inspect next?

* **If DNS fails:** Application Layer (DNS) and Internet Layer (IP connectivity).
* **If HTTP 500 appears:** Application Layer, because the server is reachable but the application is failing.

---

### Two follow-up checks in a real incident

1. Verify listening services using:

```bash
ss -tulpn
```

2. Check the HTTP response using:

```bash
curl -I <url>
```

---

# Commands Practiced

```bash
hostname -I
ip addr show
ping
tracepath
ss -tulpn
dig
curl -I
netstat -an
nc -zv
```

---

## Key Learnings

* Learned the relationship between the OSI and TCP/IP models.
* Understood where DNS, IP, TCP, HTTP, and HTTPS fit in the networking stack.
* Practiced essential Linux networking commands used during troubleshooting.
* Learned to interpret DNS responses, HTTP status codes, listening ports, routing paths, and connectivity checks.
