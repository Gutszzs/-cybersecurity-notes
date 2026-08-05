# Linux Processes and System Monitoring

My Linux study notes focused on process management, system monitoring, and resource analysis.

Understanding processes is essential for Linux administration, troubleshooting, cybersecurity investigations, and SOC operations.

---

# What Are Processes?

A process is a running instance of a program.

Every process has:

* PID (Process ID)
* Owner
* CPU usage
* Memory usage
* Execution status

To investigate running applications, Linux provides several monitoring tools.

---

# ps

The `ps` command displays information about running processes.

Example:

```bash
ps
```

Shows processes from the current terminal session.

---

## ps aux

Displays all running processes in the system.

Example:

```bash
ps aux
```

Information shown:

```text
USER   PID   %CPU   %MEM   COMMAND
```

Meaning:

* USER → Process owner
* PID → Process identification number
* %CPU → CPU usage
* %MEM → Memory usage
* COMMAND → Executed program

---

# top

The `top` command provides a real-time view of system processes.

Example:

```bash
top
```

Useful information:

* CPU usage
* Memory usage
* Running processes
* System load

Press:

```text
q
```

to exit.

---

# htop

`htop` is an interactive and improved version of `top`.

Example:

```bash
htop
```

Features:

* Easier visualization
* Process filtering
* Interactive controls
* Resource monitoring

---

# pgrep

The `pgrep` command searches for processes by name.

Example:

```bash
pgrep nginx
```

Returns the PID of processes containing "nginx".

---

# kill

The `kill` command terminates a process using its PID.

Example:

```bash
kill 1234
```

Sends a termination signal to process `1234`.

---

## kill -9

Forces process termination.

Example:

```bash
kill -9 1234
```

⚠️ Use carefully. This immediately stops the process.

---

# Process Signals

Linux uses signals to communicate with processes.

Common signals:

| Signal  | Description                   |
| ------- | ----------------------------- |
| SIGTERM | Requests graceful termination |
| SIGKILL | Forces immediate termination  |
| SIGHUP  | Reloads configuration         |

---

# Background Processes

The `&` symbol runs a command in the background.

Example:

```bash
python app.py &
```

The process continues running while the terminal remains available.

---

# Checking System Resources

## free

Shows RAM usage.

Example:

```bash
free -h
```

The `-h` option displays values in human-readable format.

Example:

```bash
free -m
```

Shows memory usage in megabytes.

---

## uptime

Shows how long the system has been running.

Example:

```bash
uptime
```

Displays:

* System uptime
* Number of users
* Load average

---

# Finding Processes

## grep

Used with pipes to filter process information.

Example:

```bash
ps aux | grep nginx
```

Shows only processes related to nginx.

---

Example:

```bash
ps aux | grep ssh
```

Searches for SSH-related processes.

---

# Monitoring Logs and Processes

Processes often generate logs that help during troubleshooting and security investigations.

Example:

```bash
tail -f /var/log/syslog
```

Monitors system logs in real time.

---

# Security Importance

Process monitoring is essential in cybersecurity.

Suspicious activity examples:

* Unknown processes running
* High CPU usage
* Programs running from unusual locations
* Unauthorized services
* Unexpected users executing commands

---

# Cybersecurity Usage

Understanding Linux processes helps with:

* Malware detection
* Incident response
* Threat hunting
* Server monitoring
* Performance troubleshooting
* SOC investigations

During an incident, analysts often check running processes to identify suspicious behavior.

