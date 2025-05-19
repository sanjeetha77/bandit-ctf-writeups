# 

# Bandit Level 5 → Level 6

## 🧩 Challenge Description

The password for the next level is stored in a file **somewhere under the `inhere` directory**, and it meets **all of the following conditions**:

- It is **human-readable**
- It is exactly **1033 bytes** in size
- It is **not executable**

Once found, use the password to SSH into `bandit6` on port 2220.

---

## 🛠 Commands You Might Use

- `find` – search for files based on properties (size, permissions, etc.)
- `file` – identify file types
- `cat` – view file contents
- `ls -la` – list files including their permissions
- `man find` – to understand and explore all options available for the `find` command

> 💡 Tip: You can use man find to view the manual page and learn about options like -size, -type, -executable, -readable, -perm, etc., which are helpful in filtering files based on multiple attributes.
> 

---

## 💻 Steps and Commands Used

```bash
# Step 1: Log in
ssh bandit5@bandit.labs.overthewire.org -p 2220

# Step 2: Move into the inhere directory
cd inhere

# Step 3: Find files that are 1033 bytes, human-readable, and not executable
find . -type f -size 1033c ! -executable

# Output shows:
# ./maybehere07/.file2

# Step 4: Read the file's contents
cat ./maybehere07/.file2

```

## ✅ Output
![image](https://github.com/user-attachments/assets/bc14566a-5cc8-4157-aaba-02f83f4ccb16)

---
