# **Bandit Level 28 → Level 29**

---

## **🧩 Challenge Description**

There is a git repository at `ssh://bandit28-git@localhost/home/bandit28-git/repo` via the port `2220`. The password for the user `bandit28-git` is the same as for the user `bandit28`.

Clone the repository and find the password for the next level.

---

## Explanation

This level focuses on **Git commit inspection**. After cloning the repository using Git over SSH, the key step is to inspect the **commit history** using `git log`, and then examine changes with `git diff`. This shows previously committed content that may have included sensitive information (like passwords) before it was removed. This is a common way to recover accidentally exposed secrets from version control history.

---

# 🛠️ Commands Used

```bash
1. Login to bandit28:

ssh bandit28@bandit.labs.overthewire.org -p 2220
Use the password from the previous level: 0ef186ac70e04ea33b4c1853d2526fa2

2. Create a temporary directory and clone the repository:

mktemp -d
cd (above created directory)
#Ensure to give the port number
git clone ssh://bandit28-git@localhost/home/bandit28-git/repo

3. Enter the repo directory:

cd repo

4. Check the Git log to inspect commit history:

git log
You’ll see a commit with a message like:
fix password display bug...

5. Check what was changed in that commit using git diff:

git diff <commit_id>
This will show you the lines that were added/removed, and one of the removed lines will include the password.
```

---

## ✅ Output
![image](https://github.com/user-attachments/assets/dad85c73-2f7b-4497-8189-3f3d078e1ffb)
![image](https://github.com/user-attachments/assets/4242fedf-743b-437f-8e59-d4865a050661)
![image](https://github.com/user-attachments/assets/9298b818-9142-4fef-85fd-f5917e128493)

---
