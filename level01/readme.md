# Bandit Level 0 → Level 1

## 🧩 Challenge Description

The password for the next level is stored in a file called `readme` located in the **home directory**.

Once you find it, use that password to log into `bandit1` using SSH (port 2220).

---

## 🛠 Commands You Might Use

- `ls`         – list files and directories
- `ls -la` – list all files including hidden ones, with detailed info
- `cat`       – view the contents of a file

---

## 💻 Steps and Commands Used

```bash
# Step 1: Log into the server
ssh bandit0@bandit.labs.overthewire.org -p 2220

# Step 2: List files in the home directory
ls

# Step 3: If needed, list all files (including hidden)
ls -la

# Step 4: Read the contents of the file
cat readme

```

---

## ✅ Output

![bandit0](https://github.com/user-attachments/assets/d47ccdd2-67d9-4574-bc1e-27185b8ca32a)


---
