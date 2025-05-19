# Bandit Level 4 → Level 5

## 🧩 Challenge Description

The password for the next level is stored in the **only human-readable file** in the `inhere` directory.

> 💡 Tip: If your terminal gets messed up, use the reset command.
> 

Once you find the password, use it to log into `bandit5` via SSH (port 2220).

---

## 🛠 Commands You Might Use

- `ls -la` – list all files in a directory, including hidden ones
- `file` – check the type of each file
- `cat` – view contents of a file

---

## 💻 Steps and Commands Used

```bash
# Step 1: Log into the server
ssh bandit4@bandit.labs.overthewire.org -p 2220

# Step 2: Go into the 'inhere' directory
cd inhere

# Step 3: List all files
ls -la

# Step 4: Identify the human-readable file
file ./*

# Step 5: View the contents of the readable file
cat ./-file07

```

## ✅ Output

---