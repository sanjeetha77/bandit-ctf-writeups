# Bandit Level 11 → Level 12

## **🧩** Challenge Description

The password for the next level is stored in the file `data.txt`, where all **lowercase (a–z)** and **uppercase (A–Z)** letters have been **rotated by 13 positions**.

This encoding is called **ROT13** — a simple letter substitution cipher that replaces a letter with the letter 13 positions after it in the alphabet.

 **How it works:**

- A becomes N, B becomes O, ..., M becomes Z
- N becomes A, O becomes B, ..., Z becomes M
- The same applies to lowercase letters.

✅ **Example:**

`Hello` → `Uryyb`

`Uryyb` → `Hello` (ROT13 is reversible!)

To decode, we use the `tr` (translate) command to map letters from A–Z to N–Z and A–M, and a–z to n–z and a–m.

---

## 🛠 Commands You Might Use

- `ls -la` – list all files
- `cat` – display file contents
- `tr` – translate or replace characters

---

## 💻 Steps and Commands Used

```bash
# Step 1: List files in the directory
ls -la

# Step 2: Check the contents of data.txt
cat data.txt

# Step 3: Apply ROT13 decoding using `tr`
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'

```

## ✅ Output
![image](https://github.com/user-attachments/assets/f56bd1f7-2c69-42a5-b325-417926e0e646)

---
