# Day 15 – Networking Concepts: DNS, IP, Subnets & Ports

## Objective

Today's goal was to understand the core networking concepts every DevOps Engineer should know, including DNS, IP addressing, IPv6, CIDR notation, subnetting basics, and common network ports.

---

# Task 1: DNS – How Names Become IPs

## What happens when you type `google.com` in a browser?

1. The browser sends a request to the DNS Resolver to find the IP address of `google.com`.
2. If the IP address is not available in the cache, the resolver queries the Root Server, TLD Server, and Authoritative DNS Server.
3. The Authoritative DNS Server returns the IP address.
4. The browser connects to that IP address and loads the website.

---

## DNS Record Types

| Record | Purpose                                                     |
| ------ | ----------------------------------------------------------- |
| A      | Maps a domain name to an IPv4 address.                      |
| AAAA   | Maps a domain name to an IPv6 address.                      |
| CNAME  | Creates an alias from one domain name to another.           |
| MX     | Specifies the mail server responsible for receiving emails. |
| NS     | Identifies the authoritative name servers for a domain.     |

---

## Command

```bash
dig google.com
```

### Sample Output

```text
;; ANSWER SECTION:
google.com.    267    IN    A    142.250.xxx.xxx
```

* **A Record:** `142.250.xxx.xxx`
* **TTL:** `267 seconds`

---

# Task 2: IP Addressing

## What is an IPv4 Address?

An IPv4 address is a **32-bit logical address** used to uniquely identify a device on a network. It consists of **four octets** separated by dots.

**Example**

```text
192.168.1.10
```

---

## What is an IPv6 Address?

IPv6 is the latest version of the Internet Protocol introduced to overcome the shortage of IPv4 addresses. It uses **128-bit addresses**, providing a much larger address space.

### Example

```text
2001:0db8:85a3:0000:0000:8a2e:0370:7334
```

### IPv4 vs IPv6

| IPv4                          | IPv6                             |
| ----------------------------- | -------------------------------- |
| 32-bit address                | 128-bit address                  |
| Four octets separated by dots | Eight groups separated by colons |
| Limited address space         | Very large address space         |
| Example: 192.168.1.10         | Example: 2001:db8::1             |

---

## Public vs Private IP

### Public IP

* Globally unique
* Assigned by the ISP
* Used to communicate over the Internet

**Example**

```text
49.x.x.x
```

### Private IP

* Used inside local networks
* Cannot be accessed directly from the Internet

**Example**

```text
192.168.1.10
```

---

## Private IPv4 Ranges

```text
10.0.0.0 - 10.255.255.255
172.16.0.0 - 172.31.255.255
192.168.0.0 - 192.168.255.255
```

---

## Command

```bash
ip addr show
```

### Example Private IP

```text
192.168.x.x
```

---

# Task 3: CIDR & Subnetting

## What does `/24` mean?

`/24` means the **first 24 bits** of the IPv4 address represent the **network**, while the remaining **8 bits** represent the **host** portion.

---

## How many usable hosts?

| CIDR | Usable Hosts |
| ---- | -----------: |
| /24  |          254 |
| /16  |       65,534 |
| /28  |           14 |

---

## Why do we subnet?

Subnetting divides a large network into smaller networks, making IP address management easier, reducing unnecessary network traffic, improving security, and making the network more organized.

---

## CIDR Table

| CIDR | Subnet Mask     | Total IPs | Usable Hosts |
| ---- | --------------- | --------: | -----------: |
| /24  | 255.255.255.0   |       256 |          254 |
| /16  | 255.255.0.0     |    65,536 |       65,534 |
| /28  | 255.255.255.240 |        16 |           14 |

---

# Task 4: Ports – The Doors to Services

## What is a Port?

A port is a **logical communication endpoint** used by applications and services. An IP address identifies a device, while a port identifies the specific application or service running on that device.

---

## Common Ports

|  Port | Service |
| ----: | ------- |
|    22 | SSH     |
|    53 | DNS     |
|    80 | HTTP    |
|   443 | HTTPS   |
|  3306 | MySQL   |
|  6379 | Redis   |
| 27017 | MongoDB |

---

## Command

```bash
ss -tulpn
```

This command displays listening TCP and UDP ports along with the processes or services using them.

### Example

| Port | Service |
| ---: | ------- |
|   22 | SSH     |
|   53 | DNS     |

---

# Task 5: Putting It Together

## 1. You run:

```bash
curl http://myapp.com:8080
```

### Networking concepts involved

* DNS resolves `myapp.com` into an IP address.
* The request is sent to the destination IP address.
* Port **8080** identifies the web application.
* HTTP is used as the communication protocol.

---

## 2. Your application cannot reach a database at `10.0.1.50:3306`.

### What would you check first?

* Verify that the destination IP address is correct.
* Check whether the MySQL service is running on Port **3306**.
* Ensure firewall or security rules allow the connection.
* Confirm network connectivity between the application and the database server.

---

# Commands Used

```bash
dig google.com
ip addr show
ss -tulpn
```

---

# Key Learnings

* DNS translates domain names into IP addresses through DNS servers.
* IPv4, IPv6, and CIDR help organize and manage network communication efficiently.
* IP addresses identify devices, while port numbers identify the applications and services running on those devices.
