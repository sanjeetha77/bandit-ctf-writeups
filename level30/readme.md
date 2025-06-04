# **Bandit Level 30 → Level 31**

---

## **🧩 Challenge Description**

There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo` via the port `2220`. The password for the user `bandit30-git` is the same as for the user `bandit30`.

Clone the repository and find the password for the next level.

---

## Explanation

- **`git tag`** lists all tags in the repository, which are often used to mark important versions or notes.
- Since `git log` didn't help, inspecting tags was a logical next step.
- **`git show <tag>`** displays the object (commit, annotation, etc.) the tag points to. In this case, the tag contains the password itself.

---

# 🛠️ Commands Used

```bash
1. Login to bandit30:

ssh bandit30@bandit.labs.overthewire.org -p 2220
Use the password from the previous level.

2. Clone the Git repository:

mktemp -d
cd (above created directory)
git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
cd repo

3. Check the Git log:

git log
No meaningful output here.

4. Check for tags:

git tag
You'll find a tag like:

secret
Try checking out the tag:

git checkout secret
You may see a message like Note: checking out 'secret', but this doesn’t directly show the password.

5. Display the tag contents:

git show secret
This will reveal the password for bandit31.
```

---

## ✅ Output
![image](https://github.com/user-attachments/assets/46bdd8fd-add3-48e9-a0a4-7319eb2a34c7)
![image](https://github.com/user-attachments/assets/aed4925d-7adc-409f-8e39-892aedc07434)

---
