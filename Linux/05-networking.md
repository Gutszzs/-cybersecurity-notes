# Linux Networking Basics

My Linux study notes focused on networking commands, IP configuration, connectivity testing, and network troubleshooting.

Understanding networking is essential for Linux administration, cybersecurity, SOC operations, and cloud environments.

---

# Network Interfaces

A network interface is the component responsible for network communication.

Linux provides commands to inspect and configure network interfaces.

---

# ip a

The `ip a` command displays detailed information about network interfaces.

Example:

```bash
ip a
```

Shows:

* Network interfaces
* IP addresses
* MAC addresses
* Interface status

---

# ip -br a

Displays network interfaces in a simplified format.

Example:

```bash
ip -br a
```

Example output:

```text
eth0     UP     192.168.1.10/24
lo       UNKNOWN 127.0.0.1
```

Useful for quickly checking IP addresses.

---

# ip -c -br a

Similar to `ip -br a`, but with colors to improve readability.

Example:

```bash
ip -c -br a
```

---

# hostname

Shows the hostname of the machine.

Example:

```bash
hostname
```

The hostname identifies a device on a network.

---

# hostname -I

Displays the IP addresses assigned to the machine.

Example:

```bash
hostname -I
```

---

# ping

The `ping` command tests connectivity between devices using ICMP packets.

Example:

```bash
ping google.com
```

Used to check:

* Network connectivity
* Latency
* Packet loss

---

# ping -c

The `-c` option defines how many packets will be sent.

Example:

```bash
ping -c 4 google.com
```

Sends 4 packets and stops automatically.

---

# DNS Testing

DNS converts domain names into IP addresses.

Example:

```text
google.com → 142.250.x.x
```

Testing DNS resolution:

```bash
ping google.com
```

If the domain resolves, DNS is working.

---

# grep with Networking Commands

The `grep` command filters command output.

Example:

```bash
ip a | grep inet
```

Shows only lines containing IPv4 addresses.

---

Example:

```bash
ps aux | grep ssh
```

Searches for SSH-related processes.

---

# curl

`curl` is used to make requests to servers using protocols such as HTTP and HTTPS.

Commonly used for:

* Testing APIs
* Checking websites
* Downloading data
* Troubleshooting applications

Example:

```bash
curl https://google.com
```

---

# curl -I

Shows only HTTP headers.

Example:

```bash
curl -I https://google.com
```

Useful to check:

* HTTP status codes
* Server information
* Response headers

Example:

```text
HTTP/2 200
```

---

# wget

`wget` downloads files from the internet.

Example:

```bash
wget https://example.com/file.zip
```

Useful for:

* Downloading tools
* Getting files from servers
* Automation scripts

---

# SSH

SSH (Secure Shell) allows remote access to another machine securely.

Example:

```bash
ssh username@192.168.1.10
```

Used for:

* Remote administration
* Server management
* Cloud access

---

# SCP

SCP copies files between machines using SSH.

Example:

```bash
scp file.txt user@192.168.1.10:/home/user/
```

Copies a file to a remote server.

---

# rsync

`rsync` synchronizes files and directories efficiently.

Example:

```bash
rsync -av folder/ backup/
```

Options:

* `-a` → Archive mode
* `-v` → Verbose output

Common uses:

* Backups
* Server synchronization
* File migration

---

# Checking Open Connections

Linux systems communicate through ports.

Examples:

* 22 → SSH
* 80 → HTTP
* 443 → HTTPS

Useful command:

```bash
ss -tulnp
```

Shows listening ports and network connections.

---

# Network Troubleshooting Workflow

A basic troubleshooting sequence:

## 1. Check interface status

```bash
ip -br a
```

## 2. Check connectivity

```bash
ping -c 4 google.com
```

## 3. Check DNS

```bash
ping google.com
```

## 4. Test HTTP connection

```bash
curl -I https://google.com
```

## 5. Check active ports

```bash
ss -tulnp
```

---

# Security Importance

Networking knowledge is essential in cybersecurity.

Security analysts use network commands to:

* Investigate suspicious connections
* Analyze communication between systems
* Troubleshoot security incidents
* Monitor servers
* Identify exposed services

Examples of suspicious activity:

* Unknown listening ports
* Unexpected external connections
* Unauthorized SSH access
* Suspicious traffic patterns

---

# Cybersecurity Usage

Linux networking skills are important for:

* SOC analysts
* Threat hunting
* Incident response
* Cloud security
* Firewall management
* SIEM investigations

Understanding how systems communicate is fundamental for cybersecurity.
