# **Bandit Level 26 → Level 27**

---

## **🧩 Challenge Description**

There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo` via the port `2220`. The password for the user `bandit27-git` is the same as for the user `bandit27`.

Clone the repository and find the password for the next level.

---

## Explanation

This level introduces interaction with a Git repository over SSH. The challenge requires you to clone a local Git repo as another user (`bandit27-git`) using the same credentials as your current user. Once cloned, the contents of the repository reveal a `README` file containing the password for the next level. This level teaches Git basics, SSH access using alternate usernames, and navigating through remote repositories.

---

# 🛠️ Commands Used

```bash
1. Login to bandit27:

ssh bandit27@bandit.labs.overthewire.org -p 2220
Use the password from the previous level.

2. Create a temporary directory and clone the repository:

mktemp -d
cd (That directory that we created by the above command)
git clone ssh://bandit27-git@localhost/home/bandit27-git/repo

3. Enter the cloned repo folder:

cd repo

4. List the files and read the password:

ls
cat README
```

---

## ✅ Output

---