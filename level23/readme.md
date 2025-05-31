# **Bandit Level 23 → Level 24**

---

## **🧩 Challenge Description**

> A program is running automatically at regular intervals from cron, the time-based job scheduler.
> 
> 
> Look in `/etc/cron.d/` for the configuration and see what command is being executed.
> 
> 🧠 **This level teaches you how to create your first shell script!**
> 
> ⚠️ Your script will be **deleted automatically after it's executed**, so be ready to make a copy somewhere.
> 

---

## 📘 Strategy

1. Inspect `/etc/cron.d/` and identify the cronjob for `bandit24`.
2. Open the cronjob file and see which script is running.
3. Open and analyze the shell script to understand how it behaves.
4. Find a way to **trick the script** into giving you the password for `bandit24`.
5. Use this method to **read the password**.

---

## 🧠 Concept: How It Works

- A cronjob runs as `bandit24`, calling `/usr/bin/cronjob_bandit24.sh`.
- That script **executes a user-controlled script** if present in `/var/spool/$myname/`.
- You are **bandit23**, so your script can go into `/var/spool/bandit23/`.
- Your shell script gets **executed as bandit24**, so you can read the `bandit24` password!

---

# 🛠️ Commands Used

```bash
1. List the cronjob files
ls -la /etc/cron.d/
output:
cronjob_bandit24

2. View the cronjob file
cat /etc/cron.d/cronjob_bandit24
Output:
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
This means that /usr/bin/cronjob_bandit24.sh runs every minute as user bandit24.

3. View the actual script
cat /usr/bin/cronjob_bandit24.sh
Output:
#!/bin/bash
myname=$(whoami)
mytarget="/tmp/${myname}password"
echo "Copying passwordfile /etc/bandit_pass/$myname to $mytarget"
cat /etc/bandit_pass/$myname > $mytarget

->Uses whoami to get the user (bandit24).
->Saves the password file to /tmp/bandit24password.

4. As bandit23, wait a minute and read the file
cat /tmp/bandit24password
```

---

## ✅ Output

---