# Linux File Permissions and Users

My Linux study notes focused on file permissions, ownership, user privileges, and access control.

Understanding permissions is essential for Linux administration, cybersecurity, SOC operations, and cloud environments.

---

# File Permissions

Linux uses a permission system to control who can read, modify, or execute files and directories.

Permissions are divided into three categories:

| Permission | Meaning |
| ---------- | ------- |
| `r`        | Read    |
| `w`        | Write   |
| `x`        | Execute |

Example:

```bash
-rwxr-xr--
```

The permissions are divided into:

```
Owner | Group | Others
 rwx  | r-x   | r--
```

---

# chmod

The `chmod` command changes file and directory permissions.

## Symbolic Mode

Add execute permission:

```bash
chmod +x script.sh
```

Remove write permission:

```bash
chmod -w file.txt
```

---

## Numeric Mode

Linux permissions can also be represented by numbers:

| Number | Permission    |
| ------ | ------------- |
| 4      | Read (`r`)    |
| 2      | Write (`w`)   |
| 1      | Execute (`x`) |

Examples:

```bash
chmod 755 script.sh
```

Permission:

```
Owner:  rwx (7)
Group:  r-x (5)
Others: r-x (5)
```

Common permissions:

```bash
chmod 644 file.txt
```

Used for regular files.

```bash
chmod 755 script.sh
```

Used for executable scripts.

---

# chown

The `chown` command changes the owner and group of a file or directory.

Example:

```bash
chown ubuntu file.txt
```

Changes the file owner to the user `ubuntu`.

---

Change owner and group:

```bash
chown ubuntu:www-data file.txt
```

Changes:

```
Owner: ubuntu
Group: www-data
```

---

# sudo

The `sudo` command allows a normal user to execute commands with administrator privileges.

Example:

```bash
sudo apt update
```

Runs the command as root.

---

Check current user:

```bash
whoami
```

---

# Root User

The root user is the administrator account in Linux.

Root has full permissions over the system.

Examples of root actions:

* Install software
* Modify system files
* Manage users
* Change permissions
* Control services

⚠️ Using root incorrectly can damage the system.

---

# Users and Groups

Linux systems organize permissions using users and groups.

A file has:

```
Owner
Group
Others
```

Example:

```bash
ls -l
```

Output:

```
-rwxr-xr-- 1 gustavo developers script.sh
```

Meaning:

```
Owner: gustavo
Group: developers
Others: read only
```

---

# Useful Commands

## id

Shows information about the current user.

Example:

```bash
id
```

---

## groups

Shows the groups a user belongs to.

Example:

```bash
groups
```

---

## passwd

Changes a user's password.

Example:

```bash
passwd
```

---

## useradd

Creates a new user.

Example:

```bash
sudo useradd newuser
```

---

## usermod

Modifies user settings.

Example:

```bash
sudo usermod -aG sudo username
```

Adds a user to the sudo group.

---

## userdel

Removes a user.

Example:

```bash
sudo userdel username
```

---

# Security Importance

Incorrect permissions can create security vulnerabilities.

Examples:

❌ Dangerous:

```bash
chmod 777 file.sh
```

Everyone can read, modify, and execute the file.

✅ Better:

```bash
chmod 750 file.sh
```

Only the owner and group have access.

---

# Cybersecurity Usage

Understanding Linux permissions is important for:

* Privilege escalation analysis
* Server hardening
* Access control
* Incident response
* Malware investigation
* Cloud security

Linux permissions are one of the first things analyzed during security investigations.

