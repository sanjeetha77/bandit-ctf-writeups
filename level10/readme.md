# Bandit Level 9 → Level 10

## **🧩** Challenge Description

The password for the next level is stored in the file `data.txt`, in one of the few human-readable strings, and is **preceded by several `=` characters**.

---

## 🛠 Commands You Might Use

- `strings` – extract printable text from a binary file
- `grep` – search for specific patterns in text
- `ls -la` – list all files in the directory
- `cat` – view file contents (not useful for binary here)
- `head` – view the first few lines of a file or output [To ensure what type of file is]

---

## 💻 Steps and Commands Used

```bash
# Step 1: Confirm the file exists
ls -la

# Step 2: Extract human-readable strings and search for lines containing '='
strings data.txt | grep =

```

## ✅ Output


---