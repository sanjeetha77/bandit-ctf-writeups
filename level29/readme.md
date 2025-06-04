# **Bandit Level 29 → Level 30**

---

## **🧩 Challenge Description**

There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo` via the port `2220`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.

---

## Explanation

This level teaches the importance of **branch enumeration in Git**. Unlike the previous level, the main branch here holds no valuable information. By using `git branch -a`, we discover a hidden branch `sploits/dev`. Switching to this branch using `git checkout`, we access the actual content containing the password in `README.md`. This demonstrates how attackers or developers might hide secrets in obscure branches if not careful.

---

# 🛠️ Commands Used

```bash
1. Login to bandit29:

ssh bandit29@bandit.labs.overthewire.org -p 2220
Use the password from the previous level

2. Clone the Git repository:

mktemp -d
cd (above created directory)
#Ensure to give the port number
git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
cd repo

3. Check the Git log:

git log
Nothing useful is shown here.

4. Check for available branches:

git branch -a

5. You'll see a hidden branch:

remotes/origin/sploits/dev
Checkout the hidden branch:
git checkout sploits/dev
Check the log again (optional):
git log
based on the log info you can use,
git diff <commit_id>
```

---

## ✅ Output

---