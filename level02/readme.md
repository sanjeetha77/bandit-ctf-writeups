# Bandit Level 1 → Level 2

## 🧩 Challenge Description

The password for the next level is stored in a file called `-` located in the **home directory**.

Once you find it, use that password to log into `bandit2` using SSH (port 2220).

---

## 🛠 Commands You Might Use

- `ls` – list files and directories
- `ls -la` – list all files including hidden ones, with detailed info
- `cat` – view the contents of a file
- `cat ./-` – use `./` represents the current directory where the file named `-` can be read

---

## 💻 Steps and Commands Used

```bash
# Step 1: Log into the server
ssh bandit1@bandit.labs.overthewire.org -p 2220

# Step 2: List all files (including hidden and special ones)
ls -la

# Step 3: View contents of the file named "-"
cat ./-

```

## ✅ Output

![bandit1](https://github.com/user-attachments/assets/588e9f49-f0d5-40e7-91e2-9a85f60b46c9)


---
