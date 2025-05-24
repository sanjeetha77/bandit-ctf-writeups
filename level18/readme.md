# **Bandit Level 18 → Level 19**

## **🧩 Challenge Description**

> The password for the next level is stored in a file named readme in the home directory.
> 
> 
> Unfortunately, someone has modified `.bashrc` to **log you out immediately** when you log in with SSH.
> 

---

## 🛠️ What You Need To Do

- You need to **bypass the normal login shell** to prevent `.bashrc` from executing and logging you out.
- Then, **read the `readme` file** which contains the password for the next level.

---

## 🔍 Concept: Bypassing the Default Shell

Normally when you SSH, it opens your default login shell (like `bash`), which executes `.bashrc`.

But you can override this behavior by specifying a **custom shell** using the `-t` and a command after login.

---

## 📘 Syntax

```bash
ssh [user]@[host] -p [port] -t [command]
```

- `p` → Specifies the custom port (`2220` for Bandit).
- `t` → Forces pseudo-terminal allocation.
- `[command]` → The shell you want to run instead of the default (`/bin/sh` is a minimal shell that doesn’t run `.bashrc`).

---

## 🖥️ Commands Used

```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 -t /bin/sh
#This logs you into Bandit Level 18 using a shell that doesn't trigger .bashrc
ls
cat readme
```

---

## ✅ Output
![WhatsApp Image 2025-05-23 at 1 03 35 AM](https://github.com/user-attachments/assets/e4379df6-0f84-4bea-a199-f2ef737aa485)

---
