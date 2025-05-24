# **Bandit Level 19 → Level 20**

## **🧩 Challenge Description**

> To gain access to the next level, you should use the setuid binary found in the home directory.
> 
> 
> Execute it **without arguments** to see how to use it.
> 
> The password is located in the **usual location**: `/etc/bandit_pass/bandit20`.
> 

---

## 🛠️ What You Need To Do

- Identify the **setuid binary** file in the current directory.
- Understand what it does by **running it without arguments**.
- Use it to read the password from `/etc/bandit_pass/bandit20`.

---

## 🔍 Concept: What is a Setuid Binary?

- A **setuid binary** is a special kind of executable that **runs with the permissions of its owner**.
- In this case, `bandit20-do` is **owned by bandit20**, so when you run it, it runs **as bandit20**, even though you're logged in as `bandit19`.
- This allows you to temporarily gain access to protected files, **like the next level’s password file**.

---

## 📘 Syntax

```bash
./bandit20-do
./bandit20-do <command>
#This means you can tell it to run any command as bandit20.

```

---

## 🖥️ Commands Used

```bash
ls -la
./bandit20-do
./bandit20-do id
./bandit20-do cat /etc/bandit_pass/bandit20
```

---

## Step-by-Step Explanation

1. `ls -la`
    
    Shows all files. You’ll see a file named `bandit20-do` with `-rwsr-x---` — the `s` means it’s a **setuid binary**.
    
2. `./bandit20-do`
    
    Running without arguments shows you how to use it. It suggests you can run commands **as bandit20**.
    
3. `./bandit20-do id`
    
    Shows your effective user ID is now **bandit20** — you have temporary permissions.
    
4. `./bandit20-do cat /etc/bandit_pass/bandit20`
    
    Displays the password of the next level!
    

## ✅ Output
![WhatsApp Image 2025-05-23 at 1 03 35 AM (1)](https://github.com/user-attachments/assets/f94cb443-e13d-4720-86cf-6acc420c6de7)

---
