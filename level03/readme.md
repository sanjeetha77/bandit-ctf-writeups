# Bandit Level 2 → Level 3

## 🧩 Challenge Description

The password for the next level is stored in a file called `spaces in this filename` located in the **home directory**.

Once you find it, use that password to log into `bandit3` using SSH (port 2220).

---

## 🛠 Commands You Might Use

- `ls` – list files and directories
- `ls -la` – list all files including hidden ones
- `cat` – view the contents of a file
- Quotes `" "` – used to handle filenames with **spaces**

---

## 💻 Steps and Commands Used

```bash
# Step 1: Log into the server
ssh bandit2@bandit.labs.overthewire.org -p 2220

# Step 2: List all files in the directory
ls -la

# Step 3: Read the file with spaces in its name
cat "spaces in this filename"

```

## ✅ Output

---