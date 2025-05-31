# **Bandit Level 22 → Level 23**

---

## **🧩 Challenge Description**

> A program is running automatically at regular intervals from cron, the time-based job scheduler.
> 
> 
> Look in `/etc/cron.d/` for the configuration and see what command is being executed.
> 
> **Goal**: Find where the cronjob/script stores the password and retrieve it to access **bandit23**.
> 

---

## 📘 Strategy

You need to:

1. Check `/etc/cron.d/` for any cronjob files related to **bandit23**.
2. See what script is being executed.
3. Read and understand the logic in the script.
4. Discover where the password is being saved.
5. Read that password file.

---

## 🧠 Concept: How It Works

- The system runs a script as **bandit23**.
- That script generates a **hash filename** based on the current user.
- It then copies the password for `bandit23` into a file in `/tmp/`.
- You can **reverse-engineer** the filename and read the file to get the password.

---

# 🛠️ Commands Used

```bash
1. List cronjob files
ls -la /etc/cron.d/
Output:
cronjob_bandit23
🧠 This shows that there is a cronjob named cronjob_bandit23.

2. Read the cronjob config file
cat /etc/cron.d/cronjob_bandit23
Output:
@reboot bandit23 /usr/bin/cronjob_bandit23.sh &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh &> /dev/null
🧠 This means the script /usr/bin/cronjob_bandit23.sh is being executed every minute by user bandit23.

3. Read the actual script being executed
cat /usr/bin/cronjob_bandit23.sh
Output:
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget

The password file /etc/bandit_pass/bandit23 is copied to /tmp/<hash>

4. Recreate the hash as bandit22 to find the file
echo I am user bandit23 | md5sum | cut -d ' ' -f 1
Output:
8ca319486bfbbc3663ea0fbe81326349
🧠 So the file to read is:
/tmp/8ca319486bfbbc3663ea0fbe81326349

5. Read the password file
cat /tmp/8ca319486bfbbc3663ea0fbe81326349
```

---

## ✅ Output

---