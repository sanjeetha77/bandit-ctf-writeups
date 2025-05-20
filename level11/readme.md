# Bandit Level 10 → Level 11

## 🧩 Challenge Description

The password for the next level is stored in the file `data.txt`, which contains **base64 encoded data**. Your goal is to decode it.

---

## 🛠 Commands You Might Use

- `ls -la` – list all files in the directory
- `head` – display the first lines of a file
- `base64 -d` – decode base64 encoded data
- `cat` – display file content

---

## 💻 Steps and Commands Used

```bash
# Step 1: Confirm that data.txt is present
ls -la

# Step 2: Peek at the content of the file (base64-encoded text)
head -5 data.txt

# Step 3: Decode the base64 encoded data
base64 -d data.txt
```

---

## 📘 Extra Tip – `base64` Command

The `base64` command is used to **encode or decode data** in base64 format.

- To decode:

```bash
base64 -d filename
```

- To encode:

```bash
b
```

---

## ✅ Output
![image](https://github.com/user-attachments/assets/1b6d5b7a-37b5-4acb-bcdc-d3ea9160cc6c)

---
