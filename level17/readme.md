# **Bandit Level 17 → Level 18**

## **🧩 Challenge Description**

> There are 2 files in the home directory: passwords.old and passwords.new.
> 
> 
> The password for the next level is in `passwords.new`, and it is the only line that has been changed between the two files.
> 

---

## 🛠️ What You Need To Do

- Compare the contents of the files `passwords.old` and `passwords.new`.
- Identify the line that differs.
- The changed line in `passwords.new` contains the password for the next level.

---

## 🔍 Command Used: `diff`

### 📌 What is `diff`?

- The `diff` command compares two files **line by line**.
- It shows the **differences** between the files: lines that were **added**, **removed**, or **modified**.
- It is useful when you want to quickly spot changes between versions of a file.

### 📘 Syntax

```bash
diff [file1] [file2]
```

- `file1`: the first file to compare.
- `file2`: the second file to compare.

> The output format:
> 
> - `42c42` → Line 42 in file1 is changed compared to line 42 in file2.
> - `<` shows the content from file1 (first file).
> - `>` shows the content from file2 (second file).

---

## 🖥️ Commands Used

```bash
ls -la
diff passwords.new passwords.old
```

---

## ✅ Output
![image](https://github.com/user-attachments/assets/0ca22fdd-6997-4304-85b2-439445998b48)

---
