# Linux Shell and Automation

My Linux study notes focused on shell operators, environment variables, command chaining, and automation concepts.

Understanding the shell is essential for Linux administration, cybersecurity, SOC operations, DevOps, and cloud environments.

---

# What is the Shell?

The shell is an interface that allows users to interact with the Linux operating system using commands.

The most common Linux shell is:

```bash
bash
```

The shell allows users to:

* Execute commands
* Manage files
* Automate tasks
* Create scripts
* Manage systems

---

# Pipes ( | )

The pipe operator sends the output of one command as input to another command.

Example:

```bash id="4k8v2a"
ls -la | grep ".txt"
```

Explanation:

1. `ls -la` lists files.
2. `grep` filters only files containing `.txt`.

---

Example with processes:

```bash id="8x1f7m"
ps aux | grep nginx
```

Shows only processes related to nginx.

---

# Output Redirection

Linux allows command output to be redirected to files.

---

# >

The `>` operator saves command output to a file.

It replaces the existing content.

Example:

```bash id="m7q3vz"
ls > files.txt
```

Creates or overwrites `files.txt`.

---

# >>

The `>>` operator adds output to the end of a file.

Example:

```bash id="p9x5nk"
echo "New log" >> logs.txt
```

Keeps existing content and adds new information.

---

# Input Redirection (<)

The `<` operator uses a file as input for a command.

Example:

```bash id="5y2k7d"
sort < names.txt
```

The content of `names.txt` is used by `sort`.

---

# Error Redirection

Linux separates:

* Standard output (`stdout`)
* Standard error (`stderr`)

---

# 2>

Redirects only error messages.

Example:

```bash id="7q3m9z"
ls invalid-folder 2> errors.txt
```

Stores errors inside `errors.txt`.

---

# 2>>

Adds errors to an existing file.

Example:

```bash id="3r9w2x"
ls invalid-folder 2>> errors.txt
```

---

# Command Chaining

Linux allows multiple commands to be connected.

---

# &&

Runs the next command only if the previous command succeeds.

Example:

```bash id="1w6p4c"
mkdir projects && cd projects
```

The second command executes only if the directory is created successfully.

---

# &

Runs a process in the background.

Example:

```bash id="9f4m7b"
python app.py &
```

The process continues running while the terminal remains available.

---

# echo

The `echo` command displays text or variable values.

Example:

```bash id="7k3p8v"
echo "Hello Linux"
```

Output:

```text
Hello Linux
```

---

## Using Variables

Example:

```bash id="4m8v2x"
NAME="Gustavo"
echo $NAME
```

Output:

```text
Gustavo
```

---

# Environment Variables

Environment variables store information used by the operating system and applications.

Examples:

* PATH
* HOME
* USER
* SHELL

---

# env

Displays environment variables.

Example:

```bash id="6v9q3z"
env
```

---

# export

Creates or modifies environment variables.

Example:

```bash id="8p2m5x"
export NAME=Gustavo
```

Check value:

```bash id="2k7w4c"
echo $NAME
```

---

# tee

The `tee` command displays output on the screen and saves it to a file.

Example:

```bash id="5z8n1m"
ls | tee files.txt
```

Result:

* Shows output in terminal
* Saves output to `files.txt`

---

# xargs

The `xargs` command converts input into arguments for another command.

Useful for automation.

Example:

```bash id="9m3q6x"
cat files.txt | xargs rm
```

Removes files listed inside `files.txt`.

---

# Command Substitution

Allows using the output of one command inside another.

Example:

```bash id="4v7n2k"
echo "Kernel: $(uname -r)"
```

Output:

```text
Kernel: Linux version
```

---

# Bash Automation Example

A simple script:

```bash
#!/bin/bash

echo "System Information"

hostname
whoami
uname -r
```

Save as:

```bash
system-info.sh
```

Give execution permission:

```bash
chmod +x system-info.sh
```

Run:

```bash
./system-info.sh
```

---

# Useful Shell Practices

Good practices:

* Use meaningful variable names
* Add comments to scripts
* Avoid running unknown scripts as root
* Test commands before automation
* Keep backups before modifying systems

---

# Security Importance

Shell knowledge is extremely important in cybersecurity.

Security professionals use the shell for:

* Log analysis
* Incident response
* Automation
* System investigation
* Threat hunting
* Security tooling

Attackers also use shell commands, making this knowledge essential for understanding and defending Linux systems.

---

# Cybersecurity Usage

Linux shell skills are useful for:

* SOC analysts
* Blue Team operations
* Cloud engineers
* DevOps professionals
* Security automation

Mastering the shell is one of the foundations for working with Linux-based environments.
