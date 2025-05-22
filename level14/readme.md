# Bandit Level 13 → Level 14

## **🧩** Challenge Description

The password for the next level is stored in `/etc/bandit_pass/bandit14`, but it can only be read by `bandit14`. However, `bandit13` has access to a private SSH key that can be used to log in as `bandit14`. Your task is to make use of this key to switch users and retrieve the password.

---

## Explanation

- First, navigate to the home directory using `ls` to locate the SSH private key file named `sshkey.private`. This file allows secure authentication without a password.
- Since SSH keys must have the correct permission to be used securely, it’s good to copy the key to a working directory (optional), and then use `chmod 600 sshkey.private` to restrict access to the key.
- Next, the SSH private key will be used to log into the `bandit14` account on the same host (localhost). The command for this is:
    
    `ssh -i sshkey.private bandit14@localhost -p 2220`
    
- Upon login, there is no password prompt, as the private key authenticates the user. You’re now inside the `bandit14` account.
- Simply run: `cat /etc/bandit_pass/bandit14` to retrieve the password for the next level.

---

## Strategy

1. View and secure the private key.
2. Use the SSH key to log into the `bandit14` account.
3. Read the password file from `/etc/bandit_pass`.

---

## 🛠️ Tools Used

- `ls` – to view files
- `chmod` – to set secure permissions
- `ssh` – to log into another user’s account using a key
- `cat` – to display the password

---

## 🖥️ Commands Used

```bash

# Step 1: List files and view the private key
ls
cat sshkey.private

# Step 2: (optional) Change permissions for key
chmod 600 sshkey.private

# Step 3: SSH into bandit14 using the private key
ssh -i sshkey.private bandit14@localhost -p 2220

# Step 4: After logging in as bandit14, display the password
cat /etc/bandit_pass/bandit14

```

---

## ✅ Output
![image](https://github.com/user-attachments/assets/45ec7347-07b2-4355-8ab8-e8b11f03c488)
![image](https://github.com/user-attachments/assets/41ec6179-7ccc-45dd-9564-257abf381307)

---
