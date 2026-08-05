# Linux Basics - Essential Commands

My Linux study notes focused on system administration, cybersecurity, SOC, and cloud environments.

---

# Navigation and File Management

## ls

Lists files and directories from the current location.

Example:

```bash
ls
```

Useful options:

```bash
ls -a
```

Shows hidden files.

```bash
ls -l
```

Shows detailed information about files.

---

## pwd

Shows the current working directory.

Example:

```bash
pwd
```

---

## cd

Changes the current directory.

Example:

```bash
cd Documents
```

Go back one directory:

```bash
cd ..
```

Go to the home directory:

```bash
cd ~
```

---

## mkdir

Creates a new directory.

Example:

```bash
mkdir studies
```

---

## touch

Creates an empty file or updates the modification date.

Example:

```bash
touch notes.txt
```

---

## cp

Copies files or directories.

Example:

```bash
cp file.txt backup.txt
```

---

## mv

Moves or renames files.

Rename:

```bash
mv old.txt new.txt
```

Move:

```bash
mv file.txt Documents/
```

---

## rm

Removes files.

Example:

```bash
rm file.txt
```

Remove directories recursively:

```bash
rm -rf folder/
```

⚠️ Be careful. This command can permanently delete data.

---

# File Reading

## cat

Displays the content of a file.

Example:

```bash
cat file.txt
```

---

## less

Allows viewing large files page by page.

Example:

```bash
less file.txt
```

Press:

```text
q
```

to exit.

---

## head

Shows the first lines of a file.

Example:

```bash
head file.txt
```

---

## tail

Shows the last lines of a file.

Example:

```bash
tail file.txt
```

Monitor logs in real time:

```bash
tail -f /var/log/app.log
```

---

# Help and Documentation

## man

Shows the manual documentation of a command.

Example:

```bash
man ls
```

---

## --help

Displays quick help information.

Example:

```bash
ls --help
```

---

# Terminal Utilities

## clear

Clears the terminal screen.

Example:

```bash
clear
```

---

## history

Shows previously executed commands.

Example:

```bash
history
```

---

## whoami

Shows the current logged-in user.

Example:

```bash
whoami
```

---

# Cybersecurity Usage

Linux commands are essential for:

* Server administration
* Log analysis
* Incident response
* Security monitoring
* Cloud environments
* SOC operations

