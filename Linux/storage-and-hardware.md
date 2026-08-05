# Linux Storage and Hardware

My Linux study notes focused on storage management, disk usage, memory analysis, and hardware information.

Understanding system resources is essential for Linux administration, cybersecurity, SOC operations, and cloud environments.

---

# Disk and Storage Management

Linux provides several tools to analyze disks, partitions, and storage usage.

---

# df

The `df` command displays information about filesystem usage.

Example:

```bash
df
```

Shows:

* Total disk space
* Used space
* Available space
* Mounted filesystems

---

## df -h

The `-h` option displays information in a human-readable format.

Example:

```bash
df -h
```

Example output:

```text
Filesystem   Size   Used   Available
/dev/sda1    50G    20G    30G
```

Commonly used to check if a server is running out of disk space.

---

# du

The `du` command shows the disk usage of files and directories.

Example:

```bash
du file.txt
```

---

## du -sh

Shows the total size of a directory in a readable format.

Example:

```bash
du -sh Downloads/
```

Example output:

```text
2.5G    Downloads/
```

---

## du -sh *

Shows the size of all files and directories in the current location.

Example:

```bash
du -sh *
```

Useful for finding what is consuming disk space.

---

# ncdu

`ncdu` is an interactive tool for analyzing disk usage.

Example:

```bash
ncdu
```

Features:

* Interactive navigation
* Directory size analysis
* Easier disk management

Useful on servers with limited storage.

---

# lsblk

The `lsblk` command displays information about block devices.

Example:

```bash
lsblk
```

Shows:

* Disks
* Partitions
* Mount points

Example:

```text
NAME   SIZE   TYPE
sda    100G   disk
├─sda1 90G    part
└─sda2 10G    part
```

---

# Memory Management

RAM usage is important for monitoring system performance.

---

# free

The `free` command displays memory usage.

Example:

```bash
free
```

Shows:

* Total memory
* Used memory
* Available memory
* Swap usage

---

## free -h

Displays memory in a human-readable format.

Example:

```bash
free -h
```

Example:

```text
              total    used    free
Mem:           8G      3G      5G
```

---

## free -m

Displays memory values in megabytes.

Example:

```bash
free -m
```

Useful for scripts and monitoring.

---

# CPU Information

Understanding hardware resources helps with troubleshooting and performance analysis.

---

# uname

The `uname` command displays system information.

Example:

```bash
uname
```

---

## uname -r

Shows the Linux kernel version.

Example:

```bash
uname -r
```

Example output:

```text
6.8.0-31-generic
```

The kernel controls communication between hardware and software.

---

# lscpu

The `lscpu` command displays CPU information.

Example:

```bash
lscpu
```

Shows:

* CPU model
* Number of cores
* Architecture
* Virtualization support

---

# Hardware Devices

Linux provides commands to inspect connected hardware.

---

# lsusb

The `lsusb` command lists USB devices connected to the system.

Example:

```bash
lsusb
```

Shows:

* USB controllers
* External devices
* Hardware information

---

# lspci

The `lspci` command lists PCI devices.

Example:

```bash
lspci
```

Shows:

* Network adapters
* Graphics cards
* Storage controllers

---

# System Resource Analysis

When troubleshooting a Linux system, a basic analysis workflow:

## Check memory:

```bash
free -h
```

---

## Check disk usage:

```bash
df -h
```

---

## Find large directories:

```bash
du -sh *
```

---

## Check hardware information:

```bash
lscpu
```

```bash
lsblk
```

---

# Security Importance

System resource analysis is important in cybersecurity.

Security analysts may investigate:

* Unexpected disk usage
* Unknown hardware devices
* Resource consumption by suspicious processes
* Storage exhaustion attacks
* System compromise indicators

Examples:

* A suspicious process consuming 100% CPU
* A server running out of disk space due to logs
* Unknown storage devices connected

---

# Cybersecurity Usage

Knowledge of Linux storage and hardware commands helps with:

* Server administration
* Incident response
* System monitoring
* Cloud infrastructure
* Performance troubleshooting
* Security investigations

Understanding system resources is essential for maintaining secure and reliable environments.
