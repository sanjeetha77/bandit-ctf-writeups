# **Bandit Level 24 → Level 25**

---

## **🧩 Challenge Description**

Logging in to **bandit26** from **bandit25** should be easy… but the shell for `bandit26` is not `/bin/bash`.

Your task:

- Find out **what shell is used**.
- Understand **how it works**.
- Find a way to **break out of it** and get the **password for bandit26**.

---

## Explanation

In this level, we are provided with a private SSH key to log into `bandit26`, but the account is restricted with a custom shell (`/usr/bin/showtext`) that runs `more` to display a message. To bypass this, we exploit a feature in `more` that lets us launch the `vi` editor by pressing `v`. From `vi`, we can then execute `:e etc/bandit_pass/bandit26` to view the password for the next level or else you can type `:e set shell=/bin/sh` to go back to shell and then type  `:shell` to enter the shell and then use `ls` to display file contents and then find the password. Key concepts used here are SSH private key authentication, shell restriction bypass via `vi`, and privilege escalation through standard Linux tools.

And to ensure that the shell needs to minimize upto the extend and then press `v` to enter into the vim editor and can view the password.

---

# 🛠️ Commands Used

```bash

1. Check the shell for bandit26:

cat /etc/passwd | grep bandit26
Output: /usr/bin/showtext

2. SSH into bandit26 using the given private key:

ssh -i bandit26.sshkey bandit26@bandit.labs.overthewire.org -p 2220
Bypass the more-based shell restriction:

3. While the message is being shown with more, press v to open the content in vi.

In vi, press :, then type:

:e /etc/bandit_pass/bandit26
This displays the password for the next level

4. View the password for bandit26:

cat /etc/bandit_pass/bandit26
```

---

## ✅ Output
![image](https://github.com/user-attachments/assets/1912c5fd-e008-475a-bdf9-e674204ea896)
![image](https://github.com/user-attachments/assets/e28b0b40-df24-4b9e-a76e-bf807962594f)
![image](https://github.com/user-attachments/assets/ca13d427-1731-441b-9e13-7505665cdff3)
![image](https://github.com/user-attachments/assets/0b735953-ace1-4c11-a209-1aa4f558ac49)

---
