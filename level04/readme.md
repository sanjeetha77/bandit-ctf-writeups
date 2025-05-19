# Bandit Level 3 → Level 4

## 🧩 Challenge Description

The password for the next level is stored in a **hidden file** inside the `inhere` directory.

Once you find it, use that password to log into `bandit4` using SSH (port 2220).

---

## 🛠 Commands You Might Use

- `ls -la` – list all files including **hidden files** (those starting with `.`)
- `cd` – change directory
- `cat` – view the contents of a file

---

## 💻 Steps and Commands Used

```bash
# Step 1: Log into the server
ssh bandit3@bandit.labs.overthewire.org -p 2220

# Step 2: List contents of the current directory
ls -la

# Step 3: Move into the 'inhere' directory
cd inhere

# Step 4: List all files including hidden ones
ls -la

# Step 5: Read the contents of the hidden file
cat ...Hiding-From-You

```

## ✅ Output

---