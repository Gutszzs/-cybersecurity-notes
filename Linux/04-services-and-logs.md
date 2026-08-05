# Linux Services and Logs

My Linux study notes focused on service management, system logs, and troubleshooting.

Understanding services and logs is essential for Linux administration, cybersecurity, SOC operations, and incident response.

---

# What Are Services?

A service is a program that runs in the background and provides functionality to the operating system or users.

Examples:

* Web servers
* Database servers
* SSH
* Network services
* Security tools

Linux uses **systemd** to manage services on most modern distributions.

---

# systemctl

The `systemctl` command is used to manage services controlled by systemd.

---

## Check Service Status

Shows the current status of a service.

Example:

```bash id="y7ak0z"
systemctl status nginx
```

Displays:

* Service status
* Recent logs
* Process information
* Errors

---

## Start a Service

Starts a stopped service.

Example:

```bash id="r3p3df"
sudo systemctl start nginx
```

---

## Stop a Service

Stops a running service.

Example:

```bash id="cxjv44"
sudo systemctl stop nginx
```

---

## Restart a Service

Restarts a service.

Useful after configuration changes.

Example:

```bash id="f7mbx3"
sudo systemctl restart nginx
```

---

## Enable a Service

Makes a service start automatically when the system boots.

Example:

```bash id="f5a9sw"
sudo systemctl enable nginx
```

---

## Disable a Service

Prevents a service from starting automatically.

Example:

```bash id="j9f5cu"
sudo systemctl disable nginx
```

---

# List Running Services

Shows all active services.

Example:

```bash id="5j34kd"
systemctl list-units --type=service
```

---

# Check Failed Services

Shows services that failed to start.

Example:

```bash id="xq3l3y"
systemctl --failed
```

Useful for troubleshooting.

---

# journalctl

The `journalctl` command is used to view logs collected by systemd.

Logs are essential for troubleshooting and security investigations.

---

# View All Logs

Example:

```bash id="5s2j0k"
journalctl
```

Displays system logs.

---

# View Logs From a Specific Service

Example:

```bash id="q1ps4n"
journalctl -u nginx
```

Shows only nginx service logs.

---

# Follow Logs in Real Time

Similar to `tail -f`.

Example:

```bash id="0z3q9u"
journalctl -f
```

Displays new logs as they appear.

---

# View Recent Logs

Example:

```bash id="4uhz8m"
journalctl -n 50
```

Shows the last 50 log entries.

---

# View Logs From Current Boot

Example:

```bash id="8h7z8k"
journalctl -b
```

Shows logs generated since the system started.

---

# Log Analysis

Logs are records of system activity.

They can contain information about:

* User authentication
* System errors
* Service failures
* Network events
* Security events

Common log locations:

```text id="x6tj7v"
/var/log/
```

Examples:

```text id="2w7g1u"
/var/log/auth.log
/var/log/syslog
/var/log/kern.log
```

---

# Authentication Logs

Authentication logs record login activity.

Example:

```bash id="o8f1r2"
cat /var/log/auth.log
```

Useful for investigating:

* Failed login attempts
* SSH access
* Privilege changes

---

# Searching Logs

Using `grep` to filter information.

Example:

```bash id="z1sk3h"
journalctl | grep error
```

Searches for logs containing "error".

---

Example:

```bash id="2h5j9f"
cat /var/log/auth.log | grep failed
```

Finds failed authentication attempts.

---

# Monitoring Logs in Real Time

Example:

```bash id="n9t6zy"
tail -f /var/log/syslog
```

Useful for monitoring:

* Application activity
* Errors
* Security events

---

# Security Importance

Services and logs are extremely important in cybersecurity.

Security analysts use logs to:

* Investigate incidents
* Detect suspicious behavior
* Analyze attacks
* Identify unauthorized access
* Perform threat hunting

Examples of suspicious activity:

* Multiple failed SSH logins
* Unknown services running
* Unexpected system changes
* Privilege escalation attempts

---

# Cybersecurity Usage

Knowledge of Linux services and logs is important for:

* SOC analysts
* Incident response
* SIEM monitoring
* Threat hunting
* Server hardening
* Cloud environments

Logs are often the primary source of evidence during a security investigation.

