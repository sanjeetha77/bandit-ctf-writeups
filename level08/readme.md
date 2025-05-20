# Bandit Level 7 → Level 8

## 🧩 Challenge Description

The password for the next level is stored in the file `data.txt`, **next to the word `millionth`**.

---

## 🛠 Commands You Might Use

- `ls -la` – list all files, including hidden ones
- `cat` – display file contents
- `grep` – search for specific patterns in files

---

## 💻 Steps and Commands Used

```bash
# Step 1: List files in the current directory
ls -la

# Step 2: Search for the word 'millionth' in data.txt
cat data.txt | grep "millionth"

```

## ✅ Output

---