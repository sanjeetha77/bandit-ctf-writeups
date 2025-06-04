# **Bandit Level 31 → Level 32**

---

## **🧩 Challenge Description**

There is a git repository at `ssh://bandit31-git@localhost/home/bandit31-git/repo` via the port `2220`. The password for the user `bandit31-git` is the same as for the user `bandit31`.

Clone the repository and find the password for the next level.

---

## Explanation

- The Git repo is set up to **return the next password** when a valid commit is pushed.
- This tests your knowledge of **Git commits**, **remote pushing**, and **authenticating via SSH**.
- You didn't need to inspect history, tags, or branches—just follow instructions and push a change.

---

# 🛠️ Commands Used

```bash
1. Login to bandit30:

ssh bandit30@bandit.labs.overthewire.org -p 2220
Use the password from the previous level.

2. Clone the Git repository:

mktemp -d
cd (above created directory)
git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo
cd repo

3. Open README.md:
cat README.md
It tells you to make a change to the file and push it back.

4. create a file called key.txt and write the cintents into the file which is in README.md file
nano key.txt

5. Commit and push:

git add README.md
git commit -m "updated readme"
git push origin main
During push, it will prompt for the bandit31 password. Paste it.

After the push, you'll see in the response from the server and can find the password .
```

---

## ✅ Output
![image](https://github.com/user-attachments/assets/3b2640c1-ae69-48ab-9b0a-7d70029aac6e)
![image](https://github.com/user-attachments/assets/5b3481d7-fb42-432c-a4a4-f42301fc2448)

---
