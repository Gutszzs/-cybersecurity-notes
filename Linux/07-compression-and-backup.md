# Linux Backup and Compression

My Linux study notes focused on file compression, archive management, and backup synchronization.

Understanding these tools is essential for Linux administration, server management, cloud environments, and cybersecurity operations.

---

# Why Compression and Backup Matter

Compression reduces file size, making storage and data transfer more efficient.

Backups help protect data against:

* Hardware failures
* Accidental deletion
* System compromise
* Data loss
* Cybersecurity incidents

---

# tar

The `tar` command is used to create and extract archive files.

It is one of the most commonly used tools for Linux backups.

---

## Create an Archive

Example:

```bash id="2n7b9f"
tar -cvf backup.tar folder/
```

Options:

| Option | Meaning          |
| ------ | ---------------- |
| `c`    | Create archive   |
| `v`    | Show process     |
| `f`    | Specify filename |

---

## Create a Compressed Archive

Using gzip compression:

```bash id="f8z7m2"
tar -czvf backup.tar.gz folder/
```

Options:

| Option | Meaning          |
| ------ | ---------------- |
| `z`    | gzip compression |
| `c`    | create           |
| `v`    | verbose          |
| `f`    | filename         |

---

## Extract an Archive

Example:

```bash id="3w8x2a"
tar -xzvf backup.tar.gz
```

Options:

| Option | Meaning    |
| ------ | ---------- |
| `x`    | Extract    |
| `z`    | gzip       |
| `v`    | Show files |
| `f`    | File       |

---

# zip

The `zip` command creates compressed ZIP files.

Example:

```bash id="j9d4qh"
zip backup.zip file.txt
```

---

## Compress a Directory

Use the `-r` option for recursive compression.

Example:

```bash id="n7v5bx"
zip -r backup.zip folder/
```

The `-r` option includes all files and subdirectories.

---

# unzip

The `unzip` command extracts ZIP files.

Example:

```bash id="8sh1xw"
unzip backup.zip
```

Extracts all files into the current directory.

---

# rsync

The `rsync` command synchronizes files and directories.

It is commonly used for:

* Backups
* Server synchronization
* Data migration
* Cloud environments

---

## Basic Usage

Example:

```bash id="q4s8z9"
rsync folder/ backup/
```

Copies files from one directory to another.

---

## Archive Mode

Example:

```bash id="x3p1vj"
rsync -a folder/ backup/
```

The `-a` option preserves:

* Permissions
* Ownership
* Timestamps
* Directory structure

---

## Verbose Mode

Example:

```bash id="k2d6pm"
rsync -av folder/ backup/
```

The `-v` option displays the transfer process.

---

## Remote Backup with SSH

Example:

```bash id="t8c5km"
rsync -av folder/ user@server:/backup/
```

Copies files to a remote server using SSH.

---

# Backup Example Workflow

A simple backup process:

## 1. Create archive

```bash id="6m5z9q"
tar -czvf backup.tar.gz important-files/
```

---

## 2. Transfer backup

```bash id="p3x9hf"
scp backup.tar.gz user@server:/backup/
```

---

## 3. Verify files

```bash id="d6r4ph"
ls -lh /backup/
```

---

# Checking File Sizes

Before creating backups, it is useful to analyze storage usage.

Example:

```bash id="g7x2qd"
du -sh folder/
```

Shows the total size of a directory.

---

# Compression Comparison

| Tool  | Main Usage                       |
| ----- | -------------------------------- |
| tar   | Linux archives and backups       |
| zip   | Portable compressed files        |
| unzip | Extract ZIP files                |
| rsync | File synchronization and backups |

---

# Security Importance

Backup knowledge is important in cybersecurity because backups are critical during incidents.

Security teams use backups for:

* Disaster recovery
* Ransomware recovery
* Evidence preservation
* System restoration

Important security practices:

* Protect backup permissions
* Encrypt sensitive backups
* Store backups separately
* Regularly test restoration

---

# Cybersecurity Usage

Linux backup and compression skills are useful for:

* SOC analysts
* System administrators
* Cloud engineers
* Incident responders

Understanding backup processes helps maintain data availability and recover from security incidents.
