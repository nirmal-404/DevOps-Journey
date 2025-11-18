# 🐚 Bash Shell Scripting Guide

> Master the art of automating tasks with Bash shell scripts

---

## 📖 Table of Contents

- [What is Shell Scripting?](#-what-is-shell-scripting)
- [Understanding the Shebang](#-understanding-the-shebang)
- [Your First Script](#-your-first-script)
- [Working with Variables](#-working-with-variables)
- [Conditional Logic](#-conditional-logic)
- [Script Workflow Reference](#-script-workflow-reference)

---

## 🎯 What is Shell Scripting?

**Shell scripting** is the practice of writing a series of commands in a script file that the Linux shell (like Bash) executes automatically.

### Why Use Shell Scripts?

✅ **Automate repetitive tasks**  
✅ **System administration & maintenance**  
✅ **Create simple programs without a full programming language**  
✅ **Schedule tasks with cron jobs**  
✅ **Batch process files and data**

---

## ⚡ Understanding the Shebang

The **shebang** (`#!/bin/bash`) is a special line at the top of a script that tells the system which interpreter to use.

```bash
#!/bin/bash
```

### How It Works

- **`#!`** → Called "shebang" or "hashbang"
- **`/bin/bash`** → Path to the Bash interpreter
- Must be the **first line** of your script
- Without it, the system may not know how to execute your script

### Common Shebangs

```bash
#!/bin/bash          # Bash shell
#!/bin/sh            # System default shell
#!/usr/bin/env bash  # More portable, finds bash in PATH
#!/usr/bin/python3   # Python script
```

---

## 🚀 Your First Script

Let's create a simple "Hello World" script from scratch!

### Step 1: Create the Script File

```bash
nano firstscript.sh
```

Opens the GNU nano text editor to create or edit `firstscript.sh`.

---

### Step 2: Write the Script

In the nano editor, type:

```bash
#!/bin/bash
echo "Hello World"
```

**Save and Exit:**
1. Press `Ctrl + O` (WriteOut)
2. Press `Enter` (confirm filename)
3. Press `Ctrl + X` (exit nano)

---

### Step 3: Make It Executable

```bash
chmod +x firstscript.sh
```

🔐 This command grants execute permissions, allowing the file to run as a program.

**Understanding File Permissions:**
- `chmod` = Change mode (permissions)
- `+x` = Add execute permission
- Without this, you'll get a "Permission denied" error

---

### Step 4: Run the Script

```bash
./firstscript.sh
```

**Output:**
```
Hello World
```

🚀 The `./` tells the shell to look for the script in the current directory.

---

### 📝 Editing Your Script

To modify your script:

```bash
nano firstscript.sh
```

Update the content:

```bash
#!/bin/bash
echo "Hello World - Edited to test"
```

Save (`Ctrl + O`, `Enter`) and exit (`Ctrl + X`), then run again:

```bash
./firstscript.sh
```

**Output:**
```
Hello World - Edited to test
```

---

## 💾 Working with Variables

Variables store data that you can use throughout your script.

### Creating a Variables Script

```bash
nano variables.sh
chmod +x variables.sh
```

**Script content:**

```bash
#!/bin/bash
name="Nirmal"
echo "Hello $name!"
```

### Running the Script

```bash
./variables.sh
```

**Output:**
```
Hello Nirmal!
```

---

### Variable Syntax Rules

| Rule | Example | Description |
|------|---------|-------------|
| **No spaces around `=`** | `name="Nirmal"` ✅ | Correct assignment |
| **Spaces break it** | `name = "Nirmal"` ❌ | Will cause error |
| **Use `$` to access** | `echo $name` | Retrieves the value |
| **Quotes for strings** | `name="John Doe"` | Handles spaces in values |
| **No quotes for numbers** | `age=25` | Numbers don't need quotes |

---

### Advanced Variable Usage

```bash
#!/bin/bash

# Multiple variables
firstname="John"
lastname="Doe"
age=30

# Combining variables
echo "Full name: $firstname $lastname"
echo "Age: $age years old"

# Command substitution
current_date=$(date)
echo "Today is: $current_date"
```

---

## 🔀 Conditional Logic

Make decisions in your scripts using `if` statements.

### Creating a Conditional Script

```bash
nano conditional.sh
chmod +x conditional.sh
```

**Script content:**

```bash
#!/bin/bash
number=5
if [ $number -gt 5 ]; then
    echo "The number is greater than 5"
else
    echo "The number is not greater than 5"
fi
```

### Running the Script

```bash
./conditional.sh
```

**Output:**
```
The number is not greater than 5
```

---

### Comparison Operators

#### Numeric Comparisons

| Operator | Meaning | Example |
|----------|---------|---------|
| `-eq` | Equal to | `[ $a -eq $b ]` |
| `-ne` | Not equal to | `[ $a -ne $b ]` |
| `-gt` | Greater than | `[ $a -gt $b ]` |
| `-ge` | Greater than or equal | `[ $a -ge $b ]` |
| `-lt` | Less than | `[ $a -lt $b ]` |
| `-le` | Less than or equal | `[ $a -le $b ]` |

#### String Comparisons

| Operator | Meaning | Example |
|----------|---------|---------|
| `=` | Equal to | `[ "$a" = "$b" ]` |
| `!=` | Not equal to | `[ "$a" != "$b" ]` |
| `-z` | String is empty | `[ -z "$a" ]` |
| `-n` | String is not empty | `[ -n "$a" ]` |

---

### Advanced Conditional Example

```bash
#!/bin/bash

score=85

if [ $score -ge 90 ]; then
    echo "Grade: A"
elif [ $score -ge 80 ]; then
    echo "Grade: B"
elif [ $score -ge 70 ]; then
    echo "Grade: C"
else
    echo "Grade: F"
fi
```

---

## 📋 Script Workflow Reference

### Quick Command Sequence

For any new script, follow these steps:

```bash
# 1. Create/Edit the script
nano scriptname.sh

# 2. Make it executable
chmod +x scriptname.sh

# 3. Run the script
./scriptname.sh
```

---

### Debugging Your Scripts

Run your script with debugging enabled:

```bash
bash -x ./scriptname.sh
```

This shows each command as it executes, helping you find errors.

---

## 💡 Best Practices

### ✅ Do's

- Always include the shebang line
- Use meaningful variable names: `user_count` instead of `uc`
- Add comments to explain complex logic: `# Calculate total price`
- Test scripts with different inputs
- Handle errors gracefully
- Use quotes around variables: `"$name"` instead of `$name`

### ❌ Don'ts

- Don't use spaces around `=` in variable assignments
- Don't forget to make scripts executable with `chmod +x`
- Don't hardcode sensitive data (passwords, API keys)
- Don't assume commands will succeed (check return codes)

---

## 🎓 Next Steps

### Learning Path

1. ✅ Basic scripts (You are here!)
2. 📚 Loops (`for`, `while`)
3. 🔧 Functions
4. 📥 User input (`read` command)
5. 📊 Arrays
6. ⚙️ Command-line arguments (`$1`, `$2`, etc.)
7. 🔍 Error handling and exit codes

---

## 📚 Additional Resources

- [Bash Guide for Beginners](https://tldp.org/LDP/Bash-Beginners-Guide/html/)
- [ShellCheck](https://www.shellcheck.net/) - Online script validator
- [Bash Cheat Sheet](https://devhints.io/bash)

---

## 🎯 Practice Exercises

Try creating these scripts on your own:

1. **Greeting Script**: Ask for user's name and greet them
2. **Calculator**: Take two numbers and perform basic operations
3. **File Backup**: Copy files from one directory to another with timestamp
4. **System Info**: Display system information (hostname, uptime, disk space)
