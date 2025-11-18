# 🐧 WSL & Linux Command Reference

> A quick reference guide for essential Windows Subsystem for Linux (WSL) and Linux terminal commands

---

## 📋 Table of Contents

- [WSL Management](#-wsl-management)
- [Navigation & Directory Operations](#-navigation--directory-operations)
- [File Operations](#-file-operations)
- [Search & Find](#-search--find)

---

## 🖥️ WSL Management

### List All WSL Distributions

```bash
wsl --list --verbose
```

**Description:** Lists all installed WSL distributions with detailed status information including running state and WSL version (1 or 2).

**Example Output:**
```
  NAME            STATE           VERSION
* Ubuntu-22.04    Running         2
  Debian          Stopped         2
```

---

### Start Specific Distribution

```bash
wsl -d Ubuntu-22.04
```

**Description:** Launches a specific WSL distribution by name.

---

### Start Default Distribution

```bash
wsl
```

**Description:** Opens your default WSL distribution and starts a Linux terminal session.

---

## 📂 Navigation & Directory Operations

### Print Working Directory

```bash
pwd
```

**Description:** Displays the full path of your current directory location.

**Example Output:** `/home/username/projects`

---

### List Files (Detailed)

```bash
ls -l
```

**Description:** Lists files and directories in long format, showing permissions, owner, size, and modification date.

**Example Output:**
```
-rw-r--r-- 1 user user 1234 Nov 18 10:30 file.txt
drwxr-xr-x 2 user user 4096 Nov 18 09:15 folder
```

---

### List All Files (Including Hidden)

```bash
ls -a
```

**Description:** Lists all files including hidden files (those starting with `.`).

---

### Create New Directory

```bash
mkdir test
```

**Description:** Creates a new directory named `test` in the current location.

---

## 📝 File Operations

### Create or Update File

```bash
touch test.txt
```

**Description:** Creates an empty file named `test.txt`. If the file already exists, updates its timestamp to the current time.

---

### Delete File

```bash
rm test.txt
```

**Description:** Permanently deletes the file `test.txt`.

⚠️ **Warning:** This action cannot be undone!

---

### Delete Directory Recursively

```bash
rm -r test
```

**Description:** Deletes the `test` directory along with all its contents (files and subdirectories).

⚠️ **Warning:** Use with caution! This removes everything inside the directory.

---

### Move or Rename

```bash
mv test/test.txt test2
```

**Description:** Moves the file `test/test.txt` into the `test2` directory. If `test2` is a filename, it renames the file instead.

**Usage Examples:**
- Move: `mv file.txt /home/user/documents/`
- Rename: `mv oldname.txt newname.txt`

---

## 🔍 Search & Find

### Find Files by Name

```bash
find /path/to/the/file --name "test.txt"
```

**Description:** Recursively searches for files named `test.txt` starting from the specified path and displays all matching locations.

**Example Output:**
```
/path/to/the/file/test.txt
/path/to/the/file/subfolder/test.txt
```

---

### Search Text Within Files

```bash
grep "hello2" test2/test.txt
```

**Description:** Searches for the text pattern `"hello2"` inside `test2/test.txt` and displays all matching lines.

**Useful Options:**
- `-i` : Case-insensitive search
- `-n` : Show line numbers
- `-r` : Recursive search through directories

**Example:**
```bash
grep -in "hello2" test2/test.txt
```

---

## 💡 Pro Tips

- Use `Tab` key for auto-completion of commands and file names
- Use `↑` and `↓` arrow keys to navigate through command history
- Use `Ctrl + C` to cancel a running command
- Use `clear` or `Ctrl + L` to clear the terminal screen
- Combine commands with `&&` to run them sequentially: `mkdir folder && cd folder`

---

## 📚 Additional Resources

- [Official WSL Documentation](https://docs.microsoft.com/en-us/windows/wsl/)
- [Linux Command Line Basics](https://ubuntu.com/tutorials/command-line-for-beginners)
